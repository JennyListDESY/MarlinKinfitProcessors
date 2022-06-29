# v00-05

* 2022-06-28 Thomas Madlener ([PR#18](https://github.com/iLCSoft/MarlinKinfitProcessors/pull/18))
  - Make doxygen cmake config work with newer cmakes (>= 3.17)

* 2022-05-17 JennyListDESY ([PR#17](https://github.com/iLCSoft/MarlinKinfitProcessors/pull/17))
  - bug fix in ZHllqq5CFit for usage of fixed JER

* 2022-04-20 Jenny List ([PR#16](https://github.com/iLCSoft/MarlinKinfitProcessors/pull/16))
  - preparations towards a MarlinKinfit tutorial:
      - fixing CMakeLists.txt to include MarlinUtil
      - adding an ee->ZH->llqq example with up-to-date ErrorFlow, based on work from Yasser Radkhorrami and Julie Torndal
  - example steering still assumes availability of two private processors, which are yet to be made available in a next step.

* 2022-04-04 Thomas Madlener ([PR#15](https://github.com/iLCSoft/MarlinKinfitProcessors/pull/15))
  - Migrate CI to github actions and remove travis CI setup

# v00-04-02

* 2020-06-26 Yasser Radkhorrami ([PR#12](https://github.com/iLCSoft/MarlinKinFitProcessors/pull/12))
  - FourMomentumCovMat, algebraImplementation:
     - the lower triangle of CovMatrix should be applied for correct diagonal and off-diagonal elements

* 2020-06-11 Yasser Radkhorrami ([PR#11](https://github.com/iLCSoft/MarlinKinFitProcessors/pull/11))
  1. derivatives for calculating errors of jet angles are corrected now:
         **d_theta / d_px = px . pz / ( P^2 . pT )**
         **d_theta / d_py = py . pz / ( P^2 . pT )**
         **d_theta / d_pz = -pT / P^2**
  2. JetResTheta is corrected (sqrt was missed):
     **JetResTheta = sqrt ( (d_theta / d_px)^2 * SigPx2 + ... )**
  
  3. JetResPhi is corrected (sqrt was missed, d_theta / d_px and d_theta / d_py should be replaced by d_phi / d_px and d_phi / d_py ):
     **JetResPhi = sqrt ( (d_phi / d_px)^2 * SigPx2 + ...  )**

# v00-04-01

* 2019-10-07 Remi Ete ([PR#7](https://github.com/iLCSoft/MarlinKinfitProcessors/pull/7))
  - Fixed usage of streamlog. Using streamlog macros now

* 2019-09-26 Sukeerthi Dharani ([PR#6](https://github.com/iLCSoft/MarlinKinfitProcessors/pull/6))
  - Neutrino energy correction is implemented using Yasser Radkhorrami's NuCorrector processor
  https://github.com/yradkhorrami/NuCorrector
  - ErrorFlow for jet resolution is implemented
  - Output collection with ISR, H, Z parameters is returned.

# v00-04

* 2017-12-15 Graham Wilson ([PR#4](https://github.com/iLCSoft/MarlinKinfitProcessors/pull/4))
  - Add steering files for J/psi -> mu+ mu-, Higgs -> mu+ mu-, Higgs -> mu+mu-mu+mu-, K+->pi+pi-pi+
  - eta-> pi+ pi- gamma, eta-> pi+pi-pi0
  - Fix most - but not yet all - of the compiler warnings in the MassConstraintFitter related processors.

* 2017-11-29 Graham Wilson ([PR#3](https://github.com/iLCSoft/MarlinKinfitProcessors/pull/3))
  - First commit of code of MassConstraintFitter from Justin Anguiano for 
    generalized mass-constrained fitting -- Graham. 
    Example .xml steering file is for simple use case of pi0-> gamma gamma.

* 2017-11-23 Graham Wilson ([PR#2](https://github.com/iLCSoft/MarlinKinfitProcessors/pull/2))
  - add author

* 2017-12-20 Graham Wilson ([PR#5](https://github.com/iLCSoft/MarlinKinfitProcessors/pull/5))
  - All compiler warnings now fixed.
  - Pi0Fitter.xml now configured and tested for v01-19-05-p01 test production.
  - a) angular smearing now turned off (was work-around for photon position issues in v01-19-04)
  - b) energy scale set to 1.0
  - c) additional processor parameters in MCParticleFilter to deal with generator status differences

# v00-03

# v00-02

J. List
   - added ZH5CFit processor

F. Gaede
   - made compatible with c++11
   - removed -ansi -pedantic -Wno-long-long
  
# v00-01

 moved example processors to this new package in order to
 reduce cross-dependencies with MarlinReco (eg via GammaGammaFinder).
