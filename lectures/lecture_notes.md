## Astronomical Coordinates and the Pluto Lab
### 9/22/2024

#### RA and DEC
- RA and DEC: coordinates mirroring latitude and longitude
- RA is typically given in hours subdivided into minutes and seconds
- DEC is typically given in degrees subdivided into arcminutes and arcseconds
- March 21, the Sun is at 0 hours RA  and the N-S line overhead at midnight is 12 hours RA
- September 21, the Sun is at 12 hours RA  and the N-S line overhead at midnight is 0 hours RA

#### Precession
- The Earth's north pole wobbles around like a top on a 26000 period. 
- Each star has RA and DEC but that changes as the Earth precesses
- Define an equinox called __J2000__ which is direction of Earth on Jan 1, 2000
- __Epoch:__ position of star on a particular date.
- __Equinox:__ position of the coordinate system

#### The Ecliptic
- __Ecliptic__ is the plane with all of the solar system's planets
- It is NOT parallel to our equator 

#### The Galactic Plane
- Another coordinate system. Uncommon. 

#### Time
- __Universal Time (UT):__ the same as Greenwich England time
- __Local Siderial Time (LST):__ Time corresponds to whatever RA is overhead


#### Julian Dates
- Numerical/Decimal date system easy for computers

#### Airmass
- 1 airmass: straight up (zenith)
- More airmass when looking through angle 
- Best off observing straight up 
- Rule of thumb: want to observe less than 2 airmass. As close to 1

#### Summary
- In real time, Airmass and LST are important

## CCDs and Data Reduction
- In astronomy, CCDs only measure 1 wavelength at a time
- CCDs absorb photons and turn them into electrons
- Analog-to-digital converters have error each time it reads pixel: __read noise__
- Analog-to-digital converters cannot make negative numbers
- All CCDs have a __bias__ voltage so read-out is registered as positive number

- __Note:__ When reducing data, some number related to voltage - some bias voltage added 

#### Pixel-by-Pixel Properties
- bias: positive number added to each pixel
- dark current: electrons that build up over time due to thermal effects on CCDs.
- gain: Number of photoelectrons produced per photons. Conversion factor for __counts per photon__. That number is known for each detector. 
- quantum efficiency: fraction of photons detected. Correct with flat field

#### Types of Data
- Bias Frame: ideally a zero second image that captures the per-pixel bias. 
- Dark Frame: Frame with a non-zero integration time taken with the camera shutter closed. Counts are from bias and dark current
- Flat Field: Frame with non-zero integration time taken of the twilight sky or a special screen on the dome. Counts are from bias, dark 
- Science frame: each pixel in frame, counts = science*QE + dark + bias

__IF all intergration times are the same__ 
Calibrated Image = (science - dark)/(flat_bright - flat_dark)

#### Cosmic Rays make artifcats on CCDs
- Solution: take lots of images and median them 

#### Persistent Bad Pixels:
- Solution: take average of surrounding pixels. "Dither" telescope to multiple different positions

#### Saturation
- Solution: Take short enough integrations that the detector is not saturated

## Photometry
### 9/23/2024

#### The magnitude system 
 - m_1 - m_ref = -2.5 * log_10(F_1/F_ref)
 - Zero-point magnitude (vega system): says that vega is zero mag at all wavelengths. 

#### Aperture Photometry
- Sum all the pixel values within a given aperture 
- Subtract off a flat background (outer annulus) to remove from source
- Issues: If a cloud passes overhead or atmosphere changes all stars will dim by same amount

#### PSF-Fitting Photometry
- PSF (Point spread function) is the shape of the star 
- More photons near center the center of the star (kinda looks like a 2d Gaussian)
- Weighted sum using Gaussian
- Better for crowded fields to distinguish sources than aperture photometry

#### Absolute Calibration - 
- __Landolt Fields__ compare the number of counts in your star with the number of counts in a Landolt star

#### HR-Diagram
- plots v vs. b-v magnitudes
- Can fit models to determine age of cluster

## Statistics and SNR 

#### Error Analysis - Propagation of Errors 
- __Gaussian Distribution:__ In almost all cases, Gaussian error bars are the thing to use 
- __Poisson Distribution__: counting error. Anything that you can count (small number) follows this distribution. Becomes Gaussian for large lambda.

## Adaptive Optics and its Applications
### 9/25/2024

#### Why is adaptive optics needed?
- Turbulence in Earth's atmosphere causes stars to twinkle. 
- An 8" telescope without adaptive optics will make the same images as Keck without AO
- When taking short exposure image, it is diffraction limited (end up with speckles)

#### Where does turbulence come from?
- Inside of the dome, (hot air inside the dome and cool air outside) causes convection
- Wind flow over the dome causes turbulence
- Boundary layer: at nighttime the ground radiates energy causing temperature fluctuations. Best place to build telescopes is along a cliff

#### Atmospherica perturbations cause distorted wavefronts

#### Optical consequences of turbulence
- Light rays affected by turbulence make blurry images

#### How does adaptive optics help? 
- wavefront sensor and deformable mirror to correct light rays affected by turbulence (does it ~1000 times a second!!)

#### Adaptive optics increases peak intensity of point source

#### Wavefront sensor 
- Shak-Hartman wavefront sensor: Place lenslet array in front of CCD.
- From the CCD, we can model the wavefront
- Deformable mirror has a set of actuactors. (can do a piecewise linear fit of the wavefront)

#### Laser Light Star
- Use a laser beam to create a fake star to help focus the image (sharper image, more stars)

#### Adaptive optics Research
- Andy works on direct exoplanet imaging using AO

#### AO 
- Airy pattern: width of main pattern is $\lambda/D$
- What are some of the current problems with AO?
- Neptune, Io, Uranus, Titan, Pluto
- Choose three wavelengths 
- Infrared imager 