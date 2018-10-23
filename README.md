# SkyMapper
Photometric stellar parameters
-------------------------------------------------------
| ![My image](https://github.com/casaluca/SkyMapper/blob/master/images/MW.png)
|:--:| 
| *Milky Way metallicity map using 9 million stars from the catalogue here provided. No quality cuts on parallaxes, only on photometry as explained below.* |

Please find below a catalogue of stellar parameters for stars in
both the [SkyMapper survey](http://adsabs.harvard.edu/abs/2018PASA...35...10W), 
and Gaia DR2. The catalogue contains SkyMapper
['object_id'](http://skymapper.anu.edu.au/table-browser/), 
Gaia ['source_id'](https://gaia.aip.de/metadata/gdr2/gaia_source/), 
effective temperatures 'Teff', metallicities '[Fe/H]' and their uncertainties 
'e_Teff', 'e_[Fe/H]' for slightly over 9 million sources.

Teff and [Fe/H] have been derived from SkyMapper+2MASS photometry as explained
in Casagrande et al. (2018). Briefly: all photometry has been corrected for
reddening as explained in Section 5 of the paper. SkyMapper v band photometry has 
also been corrected to account for spatial variations of zero-points across the sky, see
Eq (5). Yes, zero-points are as important as boring, so please never overlook
them!
Effective temperatures come from Eq (10), which is calibrated upon a sample of 
stars with effective temperatures from the 
[InfraRed Flux Method](http://adsabs.harvard.edu/abs/2010A%26A...512A..54C). [Fe/H] are
derived using Eq (12), which is obtained using Principal Component Analysis on
a sample of 70,000 stars with spectroscopic [Fe/H] from the 
[GALAH DR2](http://adsabs.harvard.edu/abs/2018MNRAS.478.4513B) survey.

The catalogue provided here is restricted to stars passing a number of quality
cuts: 2MASS Ks quality flag ['ph_qual'](https://old.ipac.caltech.edu/2mass/releases/allsky/doc/sec1_6b.html#phqual) 
set to either 'A' or 'B', ['gal_contam'](https://old.ipac.caltech.edu/2mass/releases/allsky/doc/sec2_2a.html)
= 0, SkyMapper ['class_star'](http://skymapper.anu.edu.au/table-browser/) > 0.8, 
['prox'](http://skymapper.anu.edu.au/table-browser/) > 15, 
['e_v_psf'](http://skymapper.anu.edu.au/table-browser/) <= 0.1,
['e_g_psf'](http://skymapper.anu.edu.au/table-browser/) <= 0.04, 
Galactic latitudes > |5| degrees from the plane. This last
requirement avoids regions with very high reddening, as well as issues
with SkyMapper photometric zero-points and crowdening towards the Galactic
plane (this is all discussed in the paper). Further, only stars lying within the
range of applicability of the metallicity calibration have been considered, see 
Eq. (13) and (14) for these fiducials. If you wish to relax any of these
requirements, or apply different values of reddening, in Casagrande et al.
(2018) there is enough information for you to build your own catalogue. 

Feel free to use this data for your own scientific investigations, and please
let me know if you find anything unusual, have any question and/or suggestion.
I expect this parameters to be OK, not to be perfect! As you can see from the
paper, the metallicity calibration is rather straightforward, with minimal number 
of bands, and no prior assumptions: this makes it easy to understand how colours 
are mapped in [Fe/H], and to propagate uncertainties. The reason for using few 
bands stems from the fact photometric uncertainties are still rather large in 
current SkyMapper photometry, i.e. unless you also introduce other assumptions, 
adding more bands with little metallicity sensitivity carries almost more noise 
than information. Hence, the  metallicity calibration currently  relies on v band, which 
has the strongest  sensitivity to [Fe/H] (see also Fig 15 in the accompanying paper. u 
band is also metallicity sensitive, but has stronger dependence on surface gravity than 
v). If you so fancy, you are  welcome to improve these metallicities by introducing priors 
and more refined approaches. The goal here is to provide the community with something reasonably 
good, reasonably soon. Also, the metallicity calibration works in a direction 
roughly parallel to the reddening vector; hence the effect of reddening is minimized 
(that is not to say that reddening has no effect! In fact, you can propagate a 
change of reddening in the metallicity calibration, and estimate its impact). 

The plots shown here suggest that stellar parameters are overall fine, but I
haven't investigated all possible trends, and I am happy for the community to
delve into this data. 
Comparison to various spectroscopic surveys (see Fig 11 and 13 in the
accompanying paper) indicates that these photometric [Fe/H] are generally good
to within 0.2 dex (rms), but do not be surprised if you occasionally find much
larger differences (mind you, the distribution of residual is very close to 
Gaussian, see insets in Fig 11 and 13). The uncertainties quoted in this catalogue 
are obtained propagatig nominal photometric errors through the Teff and [Fe/H] 
calibrations. In addition to that, for the effective temperature calibration, I added 
in quadrature a scatter of 33K (the rms of Eq 10) plus a constant systematic of 
20K (the uncertainty on the zero-point of the Teff scale). For the metallicity 
calibration, I added in quadrature an rms of 15 dex, so that the median uncertainty 
for the sample peaks approximately at 0.2 dex (the precision suggested when 
comparing to spectroscopic surveys).

| ![My image](https://github.com/casaluca/SkyMapper/blob/master/images/CMD_5mil.jpeg)
|:--:| 
| *CMD density plot when restricting the catalogue to 5 million stars with parallaxes better than 10% and other quality cuts as per [Arenou et al. (2018)](http://adsabs.harvard.edu/abs/2018A%26A...616A..17A).* |

| ![My image](https://github.com/casaluca/SkyMapper/blob/master/images/CMD_5mil_fehcal.jpeg)
|:--:| 
| *As previous figure, but colour coding by [Fe/H] instead of density. Note that the cool side of the main-sequence preferentially hosts metal poor stars, which is not what you expect. I am still looking into this, but for the time being please be aware of this problem!* |



