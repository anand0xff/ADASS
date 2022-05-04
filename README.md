# ADASS
AMI Data Analysis Summary Site

Push-down stack of AMI and KP data analysis 'milestones' or notable results to help AMI data analysis improve.  
Subdirectories - eg ./figures, or ./oifits. ./kpfits for *small* files to support summary below

Create links to eg drivercode you used, etc etc.  Commit hash numbers identifying versions of implaneia/amical/candid/... might be helpful also.

## The Summary
22.05.05 Your name here   
Summary  

    - relevant details

22.05.04 Deepashri   
Retrieved binary parameters from analysis of simulated AMI commissioning data 

    - We ran AMI Detector1, Image 2 pipeline, Kammerer's bad pixel fixing script and ImPlaneIA on three simulated exposures of AB Dor, HD37093 and 
      HD36805 observed with NRM and F480M at POS1. AB Dor was then calibrated with HD37093 and HD36805 respectively and the calibrated observables were
      stored in oifits files. The binary parameters were extracted using AMICAL/CANDID. The comparison of simulated vs retrieved parameters is given 
      below:
      
      Expected vs model binary parameters from AB Dor calibrated with HD37093
                   Expected      Model
      Sep [mas]:   374.088      374.428 +/- 3.06
      Theta [deg]: 287.640      287.263 +/- 0.45
      dm [mag]:    4.200        4.260 +/- 0.04

      Expected vs model binary parameters from AB Dor calibrated with HD36805
             Expected      Model
      Sep [mas]:   374.088      376.827 +/- 2.54
      Theta [deg]: 287.640      287.329 +/- 0.37
      dm [mag]:    4.200        4.220 +/- 0.03

22.04.28 Deepashri   
Mirage uses distorted input PSF 

    - Mirage uses a gridded PSF library to create noiseless seed images. The gridded PSF is created by calling
      psf_grid(..., add_distortion=True, ...) from WebbPSF. The distorted oversampled PSF is saved in the PRIMARY extension.
    - The distortion is applied when the gridded PSF is created by WebbPSF. Mirage uses distortion information from the SIAF 
      (sky to detector) file to place the PSF at the correct detector location. Oversampling rounding still to be resolved.


22.04.07 Anand  
Using [DoNothing](https://github.com/anand0xff/ADASS)'s (#1248a) extensive set of simulations and subsequent data analysis
tools I discovered nothing new.  

    - sim oversample/pixel scale/distortion/jitters/placement error... 
    - noise sources, (sizes,...)
    - observables ' extraction ov=1023, FFT centroid, wrong pixel scale, spectrum not matched to simulation, various other advanced features.
    - candid step size 10mas central object disk 500mas
    - Accuracy of results: bus error during core dump
