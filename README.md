# Amazon Vine Analysis: Overview

## Overview

The goal of this module is to assess Amazon reviews by contrasting data from paid reviews vs unpaid reviews. Both review types were sourced from a column in the provided data fields titled 'Vine'. Data was pulled from the dataset "amazon_reviews_us_Digital_Ebook_Purchase_v1_01". Some of the data was removed from the dataset being analyzed on the basis of the extant to which the reviews were determined to be helpful. Tools used in the analysis included Google Colab, AWS, S3, RDS, PostgresSQL nad PySpark. A review of the findings is provided below:

## Analysis


* How many Vine reviews and non-Vine reviews were there?

Our dataset did not appear to show there being any 'vine' reviws in the dataset. Upon detecting this possible anamoly, an additional test was performed using an alternative coding procedure. The same results were observed in the data. All reviews in our dataframe were non vine reviews. Specifically, there were 65149 non-vine reviws in our dataset and 0 vine reviews. 


![image](https://user-images.githubusercontent.com/95975772/169154463-8f8e0555-83b7-4f1a-bcdc-5622a201e062.png)

![image](https://user-images.githubusercontent.com/95975772/169155277-60ba3f82-c0c0-4aea-92d6-e386c801dab1.png)

![image](https://user-images.githubusercontent.com/95975772/169154999-3ab4666e-833e-45e7-9b85-972a8de65584.png)


* How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?

Our dataset indicated that there were 24673 5 star reviews within our dataframe for "non-vine" reviews. As per the prior observations, there were no "vine" reviews. It is possible that there were some vine reviews present prior to the instantiation of one of the earlier filters; however, this analysis was only performed on the dataframes after this filter was put into place.

![image](https://user-images.githubusercontent.com/95975772/169155500-bd75949a-42d9-4984-978a-ed06ed754391.png)


* What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?

Approximately 37.87% (24673 / 65149) of the reviews in the filtered 'Non-Vine' Review dataframe were 5 stars. Since there were no 'vine' reviews in the dataset, the percentage of 5 star reviews for 'vine' reviews is 0%. 


![image](https://user-images.githubusercontent.com/95975772/169156394-c2c935f4-8f14-4b9e-8be2-4f29cf76d22c.png)


## Summary

Given the information, it appears that the data files were not significantly impacted by review biases from the vine program. Once applying the filters (1: the total vote count must be 20 or greater, and 2: 50% of total votes for a given row of data must indicate they were helpful), it appears there were no vine reviews in the dataset. A future study of the data files may require a reduction in the threshold for inclusion in the data frames under review such that some vine reviews may be left in the files.

An additional data analysis was performed on only 'verified purchases' using hte dataframe of non-vine reviews. The results suggest that when calculating the percentages on only verified purchases, the ratio of 5 stars to total stared reviews decliend slightly from 37.87% to 35.67% (a decline of -2.2%). This suggests little difference between verified purchases and non-verified purchases on the total reviews submitted in Amazon. 

![image](https://user-images.githubusercontent.com/95975772/169157632-ffad6e6e-039b-4373-82b9-d3e312ceb442.png)






