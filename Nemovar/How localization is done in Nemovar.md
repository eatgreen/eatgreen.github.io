##Basically, we have one unperturbed ensemble member and several perturbed ensemble members

##Initialize the TRUE background error covariance model in order to diagnose the ensemble-based covatiance matrix


##Pseudo_ensemble initialization: **ens-par-init**  
* **ens-pseudo-init**: random(0,$B_{true}$) to  produce random fields, then balance them.
* **ens-per-init**: compute perturbation
* **ens-var-init-xd**: compute variance.
* **ens-hes-init-xd**: compute Hessian as well as the Daely tensor, eventually only the Daely tendor is stored.
* **ens-nor-xd**: normalize ensemble perturbation fields

##Initialize the covariance localization operator
###**case localized univariate**: for each variable, 
* call **cor-mod-init-3d**: correlation matrix parameters are different for each variable.
    * call **dif-mod-init-3d** initialize the diffusion operator of correlation model  
        * call **dif-D2K-init-3d** Initialize Daley to diffusion tensor conversion factors
        * call **dif-ten-alloc-3d** allocate $K11,K22,K33$
        * then fill the $K$ through different methods
            * *jp-dif-ten-hor-cst* suggests constant tensor element, call *dif-ten-hor-cst-3d* by filling $Kii$ with constant values
            * *jp-dif-ten-hor-ens* suggests ensemble-estimated call *dif-ten-hor-ens-3d* by filling $Kii$ with ensemble estimated Daley tensor.
            * *jp_dif_ten_hor_loc* suggests what?
            
###**case localized multivariate**: only one correlation matrix parameter is applied for all variable.

##Apply the $B_{ens}$ to vector $v$ leads to following:

Since we have the normalized ensemble perturbation fields and the correlation matrix parameters, when we need to apply Bens, we use Schur product. 

###In **bge-cov-opt**: 

**bge-covsqtadj-opt**, apply $B^{T/2}$:

* **case raw ensemble**:  

        allocate z_ex(N)=0
            
        for i=1:N
            apply $D^{1/2}$
            for j=1:n
                z_ex(i)=z_ex(i)+X'(j,i)*v(i)       
            end loop n
        end loop N
    
* **case univariate**：univariate formulation with a separate localization for each variable, a separate diffusion operator parameter, then
 
    * call *covenssqtadj\_opt\_3d*,
        * apply $v=D^{1/2}v$
        * call  *corenssqtadj\_opt\_3d*
            
                for i=1:N
                    
                    v=X'(:,i)*v
                
                    call cormodsqtadj_opt_3d
                                        
                        for j=1:number of diffusion
                        
                            p(:,j)=p(:,j)+C_loc^1/2 * v
                        
                        end loop number of diffusion
                    
                end loop N
            
            

* **case multivariate**： directly apply $D^{1/2}$, then $X'_b$ and $C_{loc,T}^{1/2}$.