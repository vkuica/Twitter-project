# Twitter-projectWrangling report
Quality observations
1. Changes lang header in Tweets to language and id to tweet_id in tweets data frame 2. Change value types for id, tweet_id to object
3. Need to drop / in ratings columns change data type to int for dog_rating_denom and dog_rating_num
4. Rounding float values given in the numerator to closest integer and correcting ratings after inspection
5. Change row 300 which had completely wrong rating 13/10
6. Change dog_rating_num and dog_rating_denom to integer.
7. Remove None from doggo, floofer, pupper and puppo
8. Add dog types into one column and covert into categorical type 9. Fix double dog categories
10. For 2 dogs in the picture create duplicate row and put each dog separately 11. Adding column with calculated dog score
12. Change date format to yyy-mm-dd in tweets
13. Change languages from abbreviation to full name
14. Dropping not dogs from data frame
15. Extract breed in one column
16. Drop retweets
17. Removing underscore from breed for better visuals 18. Making all breeds lowercase for comparability
Tidiness observations
1. Extract dog ra-ng from tweet text
2. Extract device type how tweet was published
3. Evaluate which columns are not needed for the research and remove them
Above is short summary of action that have performed to clean these two datasets. It is worth to mention that certain steps under quality issues can be attributed to tidiness and it is debatable were it must be placed.
First of all, after inspecting datasets I realised that many valuable information is given in the text which is impossible to use unless data is extracted. Very first steps were to extract information from Tweet text and make sure data is as accurate as possible. I chose to extract dog ratings from text and pulled it into 3 columns so I can better inspect some potential flaws (numerator, denominator and both on one). After inspecting and cleaning ratings data was converted in integer and no longer needed columns dropped.
Next step was to address quality remaining quality issues within two datasets. My research focused on chronological changes and exact time wasn’t needed for grouping. Therefore, format has been changed and hourly timestamp dropped. Additionally, columns have been renamed for data merger (ID to tweet ID) and better understanding (lang to language). Tweet ID
turned in object as it’s not something you use for calculation. Some language abbreviations were hard to understand for me so I changed them in full name.
Once this was performed I moved to cleaning picture recognition data. I first wanted to drop Tweets that have been identified as not dogs. This included objects like computer and other animals like turtle. However, this cleaning had its own limitations. I had to rely on picture recognition information which in some cases missed dogs being there as there were more items or dressed up dogs in that image. However, after doing sampling of 10 images I found out that accuracy was at 80% (might differ on another sample as this sample size is very small). I did not seed that check so you might get different results if you open all images that are in the main code. Taking this limitation into account I moved to pulling breed from 3 columns and adding into one. Standardised capital and non-capital letter, removed underscores and eventually got clean dataset. Favourited data still contains some blank cells but in visuals and conclusion outliers were dropped and it has no impact results.
Enhanced file contained dog types in 4 columns which in certain cases where 2 per tweet. I have split those rows into two because it had two dogs in it. Both remained to reflect different type. Also, some contain two types but only one was valid. Taking that into account I removed wrong one.
