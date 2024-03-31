# nyc_resto_inspections

In March 2024, I developed this Power BI dashboard at https://www.saraannkim.com/data-science-projects/coast-3ajfy-l8rg2-gd85k-4wazk-zmggw to visualize the NYC Department of Health and Mental Hygiene Restaurant Inspection Results found on the NYC Open Data site https://data.cityofnewyork.us/Health/DOHMH-New-York-City-Restaurant-Inspection-Results/43nn-pn8j/about_data.

The API call made on 3/22/2024 - using the attached file **nyc_restos_3_24_2024.ipynb** - returned a dataset containing 221,726 rows. However, 2,291 of the rows had an “inspection_date” of 1/1/1900 - which meant that they were new establishments and had not yet been inspected - so I removed those and was left with 219,435 rows. Then, I removed the 257 rows that had NA values in both the “latitude” and “longitude” columns, leaving me with 219,178 rows. I pulled the csv file I wrote (restos_2_mar_24.csv) into Power BI and noticed that there were a bunch of "0" values in the "latitude" and "longitude" columns.

I also removed 2,721 rows that had a “0” value” in both the “latitude” and “longitude” columns - using the attached file **restos_2.ipynb** - leaving me with 216,457 rows. I wrote this new dataset set to the attached csv file **restos_3_mar_24.csv**. 

Each row contains a violation code (or “N/A” if no code was found to be violated); a violation description; the restaurant name via a “dba” column and its “CAMIS” ID (record ID), phone number and address; inspection dates; scores; and other info. I wrote the dataset to a csv file, then imported it into Power BI where I created the visualizations and filters.

In this dataset, there are 25,994 restaurants represented via their unique “CAMIS” IDs; restaurants appear once or many times because each row contains a different violation code and description. So if a restaurant was written up for 13 violation codes, the same CAMIS ID appears 13 times. (It was best to find unique restaurant locations via the CAMIS ID rather than the restaurant name appearing in the “dba” column because if it’s a franchise, then the same restaurant name appears multiple times across multiple unique CAMIS IDs.)

Of the 159 violation codes that exist, 144 unique ones appear in this dataset - this includes "N/A" as a value. The full list of codes can be found at https://www.nyc.gov/assets/doh/downloads/pdf/about/healthcode/health-code-chapter23.pdf.

Violation code 10F appeared the most at 30,122 times. In the dataset, this violation states that “Non-food contact surface or equipment made of unacceptable material, not kept clean, or not properly sealed, raised, spaced or movable to allow accessibility for cleaning on all sides, above and underneath the unit,” or “Non-food contact surface improperly constructed. Unacceptable material used. Non-food contact surface or equipment improperly maintained and/or not properly sealed, raised, spaced or movable to allow accessibility for cleaning on all sides, above and underneath the unit.” Violation code 08A occurred next most frequently at 23,165 times, which says “Facility not vermin proof. Harborage or conditions conducive to attracting vermin to the premises and/or allowing vermin to exist,” or “Establishment is not free of harborage or conditions conducive to rodents, insects or other pests.” The third most common violation code was 06D at 14,540 times, which means “Food contact surface not properly washed, rinsed and sanitized after each use and following any activity when contamination may have occurred.”

In terms of cuisine type, of the 25,994 restaurants found in the dataset, the largest percentage, 18.75% (or 4,874) were American restaurants. The next largest percentage, 8.39% (or 2,181) were Chinese restaurants followed by Coffee/Tea restaurants at 7.61% (or 1,977).

The largest proportion of inspected restaurant was located in Manhattan at 38.63% (or 10,041), followed by Brooklyn at 26.02 (or 6,763)%, and then Queens at 22.87% (or 5,946).

The restaurant with the most violations was Master Wok in Brooklyn, who had 65 violation code write-ups. In a second-place tie with 59 violation code write-ups were Mee Sum Cafe, Sun Sai Gai Restaurant, and The Coppola Cafe, all in Manhattan. In third place was 3 Bros 99 Cent Pizza in Queens with 53 violation code write-ups.

# Method

1) I used the attached file 
