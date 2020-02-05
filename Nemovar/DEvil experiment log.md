##Initial tests:

ln_ens is true, estimate ensemble covariance.

### evil test with real ensemble 100 iter cgmod, with ite and loc enabled. NO variance filtering, NO LCT estimation and filtering

####Bmod

#####4 members
- [x] v1. Bmod with variance and LCT parameterized 
   * nsdv_x_mod = 1 & nten_h_x_mod = 2
- [x] v2. Bmod with variance estimated/filtered from ensemble and LCT parameterized
   * nsdv_x_mod = 5 & nten_h_x_mod = 2
- [x] v3. Bmod with variance and LCT estimated/filtered from ensemble
   * nsdv_x_mod = 5 & nten_h_x_mod = 5
- [x] v4. Bmod with variance parameterized and LCT estimated/filtered from ensemble
   * nsdv_x_mod = 1 & nten_h_x_mod = 5

#####40 members
- [] v1. Bmod with variance and LCT parameterized
   * nsdv_x_mod = 1 
- [] v2. Bmod with variance estimated/filtered from ensemble and LCT parameterized
   * nsdv_x_mod = 5 
- [x] v3. Bmod with variance and LCT estimated/filtered from ensemble 
   * nten_h_x_mod = 5

#####Bens

#####4 members
- [] v0. _Bens no localization_ not working, too noisy with high conditional number
- variance is by default ensemble estimated/filtered
- [x] v1  Bens uni-variate localization
- use ensemble estimated/filtered LCT
- [x] v2  Bens multi-variate localization
- use ensemble estimated/filtered LCT
- [x] v3  Bens uni-variate localization
- use localized/filtered LCT, should make no difference for 4 members
- [x] v4  Bens multi-variate localization
- use localized/filtered LCT
#####40 members
- [] v0. Bens no localization 
- variance is by default ensemble estimated/filtered 
- [] v1  Bens uni-variate localization **too expensive**
- use ensemble estimated/filtered LCT
- [] v2  Bens multi-variate localization
- use ensemble estimated/filtered LCT
- [] v3  Bens uni-variate localization **too expensive**
- use localization/filtered LCT
- [] v4  Bens multi-variate localization **ON GOING**
- use localization/filtered LCT