#A deformable curve and its velocity fields
##related work
particle filter, this kind of techniques are only applicable when the unknown state can be described on a reduced set of basis functions.
level set, no dynamic law
##current work
forward-backward integration process, a temporal smoothing.

##Contour representation
closed curves $\Gamma(t)$ encloding the target to track implicitly described by the zero level set of a function $\phi(x,t)=0$.
priot evolution law,
\[\frac{\partial \phi}{\partial t}+v|\nabla \phi|-\epsilon\kappa||\nabla \phi||=0
\]
###Initial contour equation
\[\phi(x,t_0)=g(x,\Gamma(t_0))+\eta_x\]
###Measurement equation
We need to devise certain techniques to associate predicted contours with the image observation.
1. we explicitly use certain segmentation technique to detect the corresponding curve.
2. we implicitly use ...

---
##Joint assimilation of motions of curves
weakly coupled da.
In my application, usually I want to track cloud systems and ocean stream structures. In summary, I am interested in tracking quatities transported by the flow. The real flow velocities are modelled explicitly through physical laws while combining the closed curve evolution law.