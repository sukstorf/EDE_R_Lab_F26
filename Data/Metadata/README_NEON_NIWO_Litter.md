# NEON Niwot Ridge litter dataset


## Summary
This dataset was prepared for Environmental Data Analytics (ENV 700) at Duke University, Fall 2026

The dataset contains data from monitoring at the Niwot Ridge Long-Term Ecological Research (LTER) station, comprising trap data for litter and small woody debris 2016-2026. 

## Database Information
Data were collected from the National Ecological Observatory Network (NEON)'s Data Products Site (https://data.neonscience.org/data-products/explore). "Litter" was inputted into the Search Bar and "Litterfall and fine woody debris production and chemistry" was selected (https://data.neonscience.org/data-products/DP1.10033.001)

RELEASE-2026 was chosen (https://www.neonscience.org/release-2026), extracting data from Jan 2016 to Dec 2024. Then the site "NIWO" was selected and all "basic" data for this site were downloaded. Data were downloaded as a zip file that included a separate data folder for each month of sampling. 

The following Python code is used to extract the litter and trap data CSV as well as the user guide. 

```python
#Import packages 
import shutil
from neonutilities as nu

#Expand the zip file
nu.stack_by_table('Neon_litterfall.zip')

#Rename litter and trap files to root folder, also user guide
shutil.move('Neon_litterfall/stackedFiles/ltr_massdata.csv','NEON_NIWO_Litter_massdata_2016-26_raw.csv')
shutil.move('Neon_litterfall/stackedFiles/ltr_pertrap.csv','NEON_NIWO_Litter_trapdata_raw.csv')
shutil.move('Neon_litterfall/NEON_LTR_userGuide_vF.pdf','NEON_Litterfall_UserGuide.pdf')

#Remove the Neon_litterfall folder
shutil.rmtree('Neon_litterfall')
```

Data were accessed 2026-06-12.

## Data Content Information

See the `NEON_LItterfall_UserGuide.pdf` metadata file for more information about column headers and codes. 

## Additional Information and Support
For more information, please contact the data assembler, **John Fay** (john.fay@duke.edu)