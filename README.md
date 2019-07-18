# SkyMapper
Photometric stellar parameters
-------------------------------------------------------
| ![My image](https://github.com/casaluca/SkyMapper/blob/master/images/MW.png)
|:--:| 
| *Milky Way metallicity map using 9 million stars from the catalogue here provided. No quality cuts on parallaxes, only on photometry as explained below. In this Cartesian frame, the Sun is located at 0,0.* |

Please find below a catalogue of photometric stellar parameters for 9+ million stars in
common between the [SkyMapper survey](http://adsabs.harvard.edu/abs/2018PASA...35...10W), 
and Gaia DR2. Teff and [Fe/H] have been derived from SkyMapper+2MASS photometry as explained
in [Casagrande et al. (2019)](https://ui.adsabs.harvard.edu/abs/2019MNRAS.482.2770C/abstract). Briefly: all photometry has 
been corrected for reddening as explained in Section 5 of the paper. SkyMapper v band photometry has 
also been corrected to account for spatial variations of zero-points across the sky, see
Eq (5). Yes, zero-points are as important as boring, so please never overlook
them!
Effective temperatures come from Eq (10), which is calibrated upon a sample of 
86,000 stars with effective temperatures from the 
[InfraRed Flux Method](http://adsabs.harvard.edu/abs/2010A%26A...512A..54C). [Fe/H] are
derived using Eq (12), which is obtained using Principal Component Analysis on
a sample of 70,000 stars with spectroscopic [Fe/H] from the 
[GALAH DR2](http://adsabs.harvard.edu/abs/2018MNRAS.478.4513B) survey.

The catalogue provided here is restricted to stars passing a number of quality
cuts: 2MASS Ks quality flag ['ph_qual'](https://old.ipac.caltech.edu/2mass/releases/allsky/doc/sec1_6b.html#phqual) 
set to either 'A' or 'B', ['gal_contam'](https://old.ipac.caltech.edu/2mass/releases/allsky/doc/sec2_2a.html) = 0, 
['mp_flg'](https://old.ipac.caltech.edu/2mass/releases/allsky/doc/sec2_2a.html) = 0, SkyMapper ['class_star'](http://skymapper.anu.edu.au/table-browser/) > 0.8, 
['prox'](http://skymapper.anu.edu.au/table-browser/) > 15, 
['v_flags'](http://skymapper.anu.edu.au/table-browser/) = 0,
['e_v_psf'](http://skymapper.anu.edu.au/table-browser/) <= 0.1,
['g_flags'](http://skymapper.anu.edu.au/table-browser/) = 0,
['e_g_psf'](http://skymapper.anu.edu.au/table-browser/) <= 0.04, 
Galactic latitudes > |5| degrees from the plane. This last
requirement avoids regions with very high reddening, as well as issues
with SkyMapper photometric zero-points and crowdening towards the Galactic
plane (this is all discussed in the paper). Further, only stars lying within the
range of applicability of the metallicity calibration have been considered, see 
Eq. (13) and (14) for these fiducials. These fiducials limit the lowest 
metallicity to -2.5 dex, so you will not find anything below this (because 
of the increasing fraction of carbon-enhanced stars below −2, there can be 
some stars that in fact are more metal poor, although they do not appear as such 
in the present calibration. See discussion in Section 5.1.3). On the metal-rich 
side, beware of stars above 0.5 dex. If you wish to relax any of these
requirements, or apply different values of reddening, in [Casagrande et al.
(2019)](https://ui.adsabs.harvard.edu/abs/2019MNRAS.482.2770C/abstract) there is all the information you 
need to apply the calibrations and build your own catalogue.

The plots shown here suggest that stellar parameters are overall fine, but I
haven't investigated all possible trends, and I am happy for the community to
delve into this data. 
Comparison to various spectroscopic surveys (see Fig 11 and 13 in the
accompanying paper) indicates that these photometric [Fe/H] are generally good
to within 0.2 dex (rms), but do not be surprised if you occasionally find much
larger differences (mind you, the distribution of residual is very close to 
Gaussian, see insets in Fig 11 and 13). The uncertainties quoted in this catalogue 
are obtained propagatig nominal photometric errors through the Teff and [Fe/H] 
calibrations. In addition to that, for the effective temperature calibration, a 
scatter of 33K (the rms of Eq 10) is added in quadrature. A constant systematic of 
20K is further included (the uncertainty on the zero-point of the Teff scale). For 
the metallicity calibration, an rms of 15 dex is added in quadrature, so that the 
median uncertainty for the sample peaks approximately at 0.2 dex (the precision 
suggested when comparing to spectroscopic surveys).

Feel free to use this data for your own scientific investigations, and please
let me know if you find anything unusual, have any question and/or suggestion.
I expect these parameters to be OK, not to be perfect! As you can see from the
paper, the metallicity calibration is rather straightforward, with minimal number 
of bands, no priors nor modelling involved. I am not claiming this is the best 
approach, but it allows to readily understand how colours are mapped into [Fe/H], and 
to propagate uncertainties. The reason for using few 
bands stems from the fact photometric uncertainties are still rather large in 
current SkyMapper photometry, i.e. unless you also introduce other assumptions, 
adding more bands with little metallicity sensitivity carries almost more noise 
than information. Hence, the  metallicity calibration currently  relies on v band, which 
has the strongest  sensitivity to [Fe/H] (see also Fig 15 in the accompanying paper. u 
band is also metallicity sensitive, but has stronger dependence on surface gravity than 
v). You are  welcome to improve these metallicities by introducing more refined 
approaches, if you so fancy. The goal here is to provide the community with something reasonably 
good, reasonably soon. Also, the metallicity calibration works in a direction 
roughly parallel to the reddening vector; hence the effect of reddening is minimized 
(that is not to say that reddening has no effect! In fact, you can propagate a 
change of reddening in the metallicity calibration, and estimate its impact). 

| ![My image](https://github.com/casaluca/SkyMapper/blob/master/images/CMD_5mil.jpeg)
|:--:| 
| *CMD density plot when restricting the catalogue to 5 million stars with parallaxes better than 10% and quality cuts (1) and (3) as per [Arenou et al. (2018)](http://adsabs.harvard.edu/abs/2018A%26A...616A..17A).* |

| ![My image](https://github.com/casaluca/SkyMapper/blob/master/images/CMD_5mil_fehcal.jpeg)
|:--:| 
| *As previous figure, but colour coding by [Fe/H] instead of density. Note that the cool side of the main-sequence (absolute g magnitude >4.5 or so) preferentially hosts metal poor stars, which is not what you expect. I'm still looking into this. For the time being, see discussion in the paper for calibration limits towards high surface gravities, and beware of this issue!* |

Data access
-------------------------------------------------------
The catalogue is available from the [SkyMapper](http://skymapper.anu.edu.au/_data/sm-gaia/) pages, as well as [here](https://www.dropbox.com/sh/t4b5jlz0z5s2fsp/AAB0S7S0xsJU5ripHyX8mF-qa?dl=0), as [fits](https://www.dropbox.com/s/snhzqou3m6b7okr/SMGaia.fits?dl=0) and [csv](https://www.dropbox.com/s/usngqs02qqn75te/SMGaia.csv.gz?dl=0). If you use it, please cite 
[Casagrande et al. (2019)](https://ui.adsabs.harvard.edu/abs/2019MNRAS.482.2770C/abstract) and have a look at the [ReadMe](https://www.dropbox.com/s/2kykumr56ffihjk/ReadMe.txt?dl=0). Also, you might find useful to [look at these plots](https://www.dropbox.com/sh/q8asob19eb0le3l/AAAWGqbOI9xgvYrMnLFw6yaXa?dl=0). They compare the metallicities obtained by the calibration against isochrones of known metallicity and synthetic v,g,Ks colours. These plots are color coded by whether the calibration under (blue) or overpredict (red) the metallicity of the isochrones (see also histogram in the inset for the extent of the offset). Green colour means the calibration is doing well within its quoted uncertainties. This comparison assumes that the synthetic colours used in the isochrones are perfect. Most likely they are not, but still this comparison should give some guidance on where you can trust best the metallicity calibration.

The catalogue contains SkyMapper ['object_id'](http://skymapper.anu.edu.au/table-browser/), Gaia ['source_id'](https://gaia.aip.de/metadata/gdr2/gaia_source/), effective temperature 'Teff', uncertainty 'e_Teff', metallicity 'feh' and uncertainty 'e_feh'.

If you have downloaded the file as 'SMGaia.fits', e.g., do the following in python:
```python
from astropy import table
t = table.Table()
smgaia = t.read('SMGaia.fits')
```

or in IDL:
```IDL
ftab_ext,'SMGaia.fits','SkyMapper_object_id',object_id
ftab_ext,'SMGaia.fits','Gaia_source_id',source_id
ftab_ext,'SMGaia.fits','Teff',Teff
ftab_ext,'SMGaia.fits','e_Teff',e_Teff
ftab_ext,'SMGaia.fits','feh',feh
ftab_ext,'SMGaia.fits','e_feh',e_feh
```

If instead you want to build your own catalogue, first you need to cross-match SkyMapper, Gaia and 2MASS Point Source Catalog. An example selecting a few useful columns (more than you need for the sake of the Teff and [Fe/H] calibration) with minimal quality constraints (no SkyMapper v and g flags, nor 2MASS minor planets flag) could be the following: 
```ruby
SELECT
    m.object_id, m.raj2000, m.dej2000, m.glon, m.glat, m.flags, m.u_flags, m.v_flags, m.g_flags, m.r_flags, m.i_flags, m.z_flags, m.class_star, m.u_psf, m.e_u_psf, m.v_psf, m.e_v_psf, m.g_psf, m.e_g_psf, m.r_psf, m.e_r_psf, m.i_psf, m.e_i_psf, m.z_psf, m.e_z_psf, m.ebmv_sfd, m.prox, t.pts_key, t.j_m, t.j_msigcom, t.h_m, t.h_msigcom, t.k_m, t.k_msigcom, t.ph_qual, t.bl_flg, t.cc_flg, t.gal_contam, g.source_id, g.parallax, g.parallax_error, g.astrometric_params_solved, g.visibility_periods_used, g.astrometric_chi2_al, g.astrometric_n_good_obs_al, g.phot_bp_rp_excess_factor, g.phot_g_mean_mag, g.phot_bp_mean_mag, g.phot_rp_mean_mag, g.phot_proc_mode, g.phot_variable_flag
FROM
    dr1.master m
JOIN 
    ext.twomass_psc t ON m.twomass_key1 = t.pts_key
JOIN
    ext.gaia_dr2 g ON m.gaia_dr2_id1 = g.source_id
WHERE 
    m.twomass_cat1='psc' 
    AND m.v_flags=0
    AND m.g_flags=0
    AND t.mp_flg=0
```
Note that currently [SkyMapper queries](http://skymapper.anu.edu.au/how-to-access/#tap) are limited to 1 million rows, so you will need to break the above one into smaller chunks.
