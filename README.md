# SSML Term Project

Belangrijke websites:
https://www.researchgate.net/publication/255604197_Applications_of_remote_sensing_and_GIS_for_damage_assessment
https://pubs.usgs.gov/publication/70009743
https://ieeexplore.ieee.org/document/9554054
https://download.geofabrik.de/asia/israel-and-palestine.html
https://browser.dataspace.copernicus.eu/?zoom=15&lat=31.51439&lng=34.45411&themeId=DEFAULT-THEME&visualizationUrl=https%3A%2F%2Fsh.dataspace.copernicus.eu%2Fogc%2Fwms%2F274a990e-7090-4676-8f7d-f1867e8474a7&datasetId=S2_L1C_CDAS&fromTime=2023-01-05T00%3A00%3A00.000Z&toTime=2023-01-05T23%3A59%3A59.999Z&layerId=2_TONEMAPPED_NATURAL_COLOR&demSource3D=%22MAPZEN%22&cloudCoverage=30&dateMode=SINGLE

### Data
For the analysis we are making use of Sentinel-1 and Sentinel-2 data. (#TODO korte uitleg per Sentinel geven). (#TODO Referentie kaart en hoe we met die polygons en de verschillende punten omgaan die niet binnen de huizen polygons liggen). As for the qualification of our results we will make use of the UNOSAT building damage site map (#TODO). 

### Sentinel - 1 Log intensity difference

#### Pre-Processing
Performing any analysis using SAR intensity radar maps requires preprocessing operations to obtain corrected data suitable for analysis. This study utilizes the SNAP 9.0 software created by the ESA team, and all images undergo the same preprocessing steps [4]. The first step is to radiometrically calibrate the images, followed by the application of a Lee sigma filter with a window size of 6x6 pixels to reduce speckle effects. The final step involved correcting the SAR distortions. To achieve this, we used the Range Doppler orthorectification method with a 30m SRTM 1 sec HGT DEM to project the data into the CRS WGS84. This enables the data to be used in subsequent analysis steps.

### Sentinel - 2 Gray Level Co-occurence Matrix
This image, derived from a grayscale source, computes the frequency of occurrence of a pixel with a certain gray level in relation to its adjacent pixels, whether horizontally, vertically, or diagonally. It quantifies the instances of pixel pairs with specific values and their spatial relationships, thereby mapping out the distribution of gray levels across the image. This textural analysis yields insights into the surface characteristics. This technique is extensively utilized in remote sensing for the identification of collapsed structures [1-3].

1. https://doi-org.proxy.library.uu.nl/10.1016/j.isprsjprs.2019.01.008
2. https://doi.org/10.3390/drones6120414
3. https://doi.org/10.3390/rs14246239
4. https://www.eoportal.org/other-space-activities/snap-sentinel-application-platform



Plan
GCLM werkend krijgen
Bufferzone maken rondom polygons, en juiste gebied uitknippen. Na bufferzone punten die erin vallen behouden, andere weggogoien. 
