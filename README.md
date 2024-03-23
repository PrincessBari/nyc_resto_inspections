# nyc_resto_inspections

In March 2024, I developed this Power BI dashboard to visualize the NYC Department of Health and Mental Hygiene Restaurant Inspection Results found on the NYC Open Data site https://data.cityofnewyork.us/Health/DOHMH-New-York-City-Restaurant-Inspection-Results/43nn-pn8j/about_data.

The API call made on 3/22/2024 returned a dataset containing 220,598 rows. However, 2311 of the rows had an “inspection_date” of 1/1/1900 - which meant that they were new establishments and had not yet been inspected - so I removed those and was left with 218,287 rows. Then, I found that 1140 rows had NA values in the “violation_code” column, which I removed and was left with 217,147 rows. Then, I removed the 248 rows that had NA values in both the “latitude” and “longitude” columns, leaving me with 216,899 rows. I also removed 2648 rows that had a “0” value” in both the “latitude” and “longitude” columns, leaving me with 214,251 rows. Each row contains a violation code; a violation description; the restaurant name via a “dba” column and its “CAMIS” ID, phone number and address; inspection dates; scores; and other info. I wrote the dataset to a csv file, then imported it into Power BI where I created the visualizations and filters.

In this dataset, there are 25,876 restaurants represented via their unique “CAMIS” IDs; restaurants appear once or many times because each row contains a different violation code and description. So if a restaurant was written up for 13 violation codes, the same CAMIS ID appears 13 times. (It was best to find unique restaurant locations via the CAMIS ID rather than the restaurant name appearing in the “dba” column because if it’s a franchise, then the same restaurant name appears multiple times across multiple unique CAMIS IDs.)

Of the 159 violation codes that exist, 143 unique ones appear in this dataset. The full list of codes can be found at https://www.nyc.gov/assets/doh/downloads/pdf/about/healthcode/health-code-chapter23.pdf.

Violation code 10F appeared the most at 13.98%. This violation states that “Flooring: unacceptable material used, not maintained or not clean / Non -food contact surfaces (wall, ceiling): unacceptable materials used: not maintained or not clean / Non -food contact surface (equipment, fixtures, decorative material, fans, etc.) not clean or not in working order.” Violation code 08A occurred next most frequently at 10.77%, which says “Harborage or conditions conducive to pests with pests, signs of pests / Door openings into the establishment from the outside not properly equipped when pests or signs of pests present.” The third most common violation code was 06D, which means “Food contact surface not washed, rinsed and sanitized when required.”

Of the 25,876 restaurants found in the dataset, the largest percentage, 18.69%, were American restaurants. The next largest percentage, 8.41% were Chinese restaurants followed by Coffee/Tea restaurants at 7.62%.

Of these 25,876 restaurants, the largest proportion was located in Manhattan at 38.5%, followed by Brooklyn at 26.06%, and then Queens at 22.93%.
