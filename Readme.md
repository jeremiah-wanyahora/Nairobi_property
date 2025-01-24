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
     
     - Insert an empty column B next to column A then type the following formula on cell B2:

       ```excel
       =SUBSTITUTE(A2, "KSh", "")
       ```

     - This will remove the spaces and the "KSh" denomination effectively. Flash fill to execute the formula along the whole column.

    - Remove the spaces between the numbers using the substitute function too:

       ```excel
       =VALUE(SUBSTITUTE(A2, " ", ""))
       ```
     
     - Copy the whole column B and overwrite column A using the Paste Values feature to get rid of the formula and remain with values.
     - Delete the column B
     - Next, convert the new Price column(B) from a general format to a number format.

   2. Handle missing or inconsistent data

    - Update the 'bedroom', 'bathroom' and 'House size' columns to indicate 0 for rows that correspond with the 'propertyType' of Vacant Land, Commercial Property and Industrial property.For bedrooms:

         - Insert a new column(E) beside the bedroom column 
         - Use the IF formula as follows and flash fill, then copy column E and Paste Values only onto the Bedroom column(D) and rename it Bedroom(Cleaned):
          ```excel
          =IF(B2= "Vacant Land", 0, D2)
          ```
         - Delete column E

    -For bathroom:

        - Insert a new column(F) beside the bathroom column 
        - Use the IF formula as follows and flash fill, then copy column F and Paste Values only onto the Bedroom column(E) and rename it Bathroom(Cleaned):

           ```excel
           =IF(B2= "Vacant Land", 0, E2)
           ```
        - Delete column F.

    -For House size:
         - Insert a new column(G) beside the house size column 
         - Use the IF formula as follows and flash fill, then copy column G and Paste Values only onto the Bedroom column(F) and rename it House size(Cleaned):

            ```excel
            =IF(B2= "Vacant Land", 0, F2)
            ```
         - Delete column G
     
    - Update the 'land size' column to indicate zero(0) for rows that correspond with the 'propertyType' of Apartment.

        - On column H beside the land size column, 
        - Use the IF formula as follows and flash fill, then copy column G and Paste Values only onto the Bedroom column(F) and rename it House size(Cleaned):
         ```excel
         =IF(F2= "mÂ²", 0, G2)
         ```
        - Delete column H.

   3. Spelling mistakes

      - Correct cell G21 from 399 mÂ²" to 399 mÂ²
      - Correct cell B2 from Townhuse to Townhouse    

   4. The house size and land size contains measurements on each cell. The same Substitute formula mixed with trim is used here.
       - For the house size; 
          - Insert a column to the right of column F.
          - Write the following formula on cell G2:
           ```excel
           =VALUE(SUBSTITUTE(F6, "mÂ²", ""))
           ```
          - Autofill the rest of the cells in column G.
          - Copy the column G and paste on column F to overwrite the column F with the new values without the measurements. Use Paste Values so as to not get an error.
          - Make sure to indicate the measurements in brackets beside the column header, house size.
          -Delete column G.
      
       - For the land size;
          - Write the following formula on cell H2;
           ```excel
           =VALUE(SUBSTITUTE(H2, "acres", ""))
           ```
          - Autofill the rest of the cells in column H.
          - Copy the column H and paste on column F to overwrite the column F with the new values without the measurements. Use Paste Values so as to not get an error.
          - Make sure to indicate the measurements in brackets beside the column header, land size.
          - Delete column H.

   5. Remove Duplicates
       - Highlight the whole dataset. (Ctrl + A)
       - Toggle to the Data pane on Excel.
       - Click on the remove duplicates option.
       - The Nairobi property dataset had 34 duplicate records removed.

   6. Create consistent formats.
      - Highlight columns with dates and numbers.
      - Choose the appropriate format on the Home pane; Home > Number format.


## Data Analysis




