# Nairobi Property Prices Analysis

- This is a project that seeks to elaborate on the variations of property prices in Nairobi, Kenya which is a rising real estate powerhouse in the region.

- Some of the key areas this project will touch on include(but are not limited to); Pricing analysis, location trends, property features and market segmentation.

## Exploratory Data Analysis

- The dataset appears to have the following columns:

1. Price: Indicates the price of the property (e.g., "KSh 350,000,000").
2. PropertyType: Specifies the type of property (e.g., Townhouse, Vacant Land, Apartment).
3. Location: The location of the property (e.g., Runda, Karen, Westlands).
4. Bedroom: The number of bedrooms.
5. Bathroom: The number of bathrooms.
6. House size: The size of the house (e.g., in square meters).
7. Land size: The size of the land (e.g., in acres).

## Data Cleaning
 ### Steps taken during the data cleaning process:
   1. The Price column is inclusive of the currency denomination, that is, 'Ksh'. The first step is to copy the dataset we are going to clean and remain with the original as is. 
   - Using the SUBSTITUTE function to remove the 'Ksh' and the commas between the figures.
     
     -Insert an empty column next to column A then type the following formula on cell B2:
     ```excel
     =TRIM(SUBSTITUTE(A2, "KSh", ""))
     ```

     -This will remove the spaces and the "KSh" denomination effectively. Flash fill to execute the formula along the whole column.
     -Copy the whole column B and overwrite column a by pasting using the Paste Special Values feature to get rid of the formula. Delete the column B
     -Next, convert the new Price column(B) from a general format to a number format.
