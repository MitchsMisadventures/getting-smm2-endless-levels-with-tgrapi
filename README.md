# Getting Endless Levels from Super Mario Maker 2 Using the TGR API

This project lets you get random Endless levels from Super Mario Maker 2 using the TGR API. I did this project in R and you can can download the file entitled `SMM2 Endless Levels API.qmd`. This of course uses The Great Rambler API [TGR API](https://tgrcode.com/mm2/docs/) for Super Mario Maker 2. This code produces a `.csv` file.

# Instructions

Download the `.qmd` file entitled `SMM2 Endless Levels API.qmd` and load it into R. From there you can follow along with the code chunks and make modifications so that the output best fits your needs.

## Code Layout

The code begins with the installation of four different packages

* httr
* jsonlite
* dplyr
* tidyr

*httr* is required so that you can actually access the API and GET infromation from it. The other three are mostly for formatting and readibility purposes. This code could definitely be optimized but I went with something that I personally felt was intuitive and easy to modify

From there, there are four code chunks that represent the four level difficulties in Super Mario Maker 2: Easy, Normal, Expert, and Super Expert. Each chunk has an `N_` variable that you can modify. This variable is where you select how many levels you want to pull from the API. After some quick testing, I found that you can't really import more than 500 levels from a difficulty at a time. You also shouldn't really be overworking the API so it makes sense for why the call count seems relatively low compared to other API's. If you want a decent amount of levels, I would recommend 250. From there you have the option of rerunning the code to get a different batch of random levels and then combining all of the dataframes into one.

Speaking of combining dataframes, there is a bit of code that deals with combining the dataframes from all four difficulties into a single one. You could of course modify this code if you didn't export levels from all four difficulties. 

From there, you can simply export the merged dataframe.

# Dictionary

| Column Name                | Column Description                            |
|----------------------------|-----------------------------------------------|
| Name                       | Level Name                                    |
| Description                | Level Description                             |
| Uploaded_Pretty            | Date Level was Uploaded                       |
| Uploaded                   | Date Level was Uploaded                       |
| Data_Id                    | Level Instance Unique Id                      |
| Course_Id                  | Course ID                                     |
| Game_Style_Name            | Level Style                                   |
| Game_Style                 | Level Style ID                                |
| Theme_Name                 | Level Theme                                   |
| Theme                      | Level Theme ID                                |
| Difficulty_Name            | Level Difficulty                              |
| Difficulty                 | Level Difficulty ID                           |
| Tags_Name_1                | Level Tag 1                                   |
| Tags_Name_2                | Level Tag 2                                   |
| Tag1                       | Level Tag 1 ID                                |
| Tag2                       | Level Tag 2 ID                                |
| World_Record_Pretty        | World Record Time                             |
| World_Record               | World Record Time (milliseconds)              |
| Upload_Time_Pretty         | Level Clear Check Time                        |
| Upload_Time                | Level Clear Check Time (milliseconds)         |
| Num_Comments               | Number of Comments                            |
| Clear_Condition            | Clear Condition ID                            |
| Clear_Condition_Magnitude  | Clear Condition Magnitude                     |
| Clears                     | Number of Level Clears                        |
| Attempts                   | Number of Level Attempts                      |
| Clear_Rate_Pretty          | Level Clear Rate (Percentage)                 |
| Clear_Rate                 | Level Clear Rate (Float)                      |
| Plays                      | Number of Level Plays                         |
| Versus_Matches             | Number of Times Level Appeared in Multiplayer |
| Coop_Matches               | Number of Times Level Appeared in Coop Mode   |
| Likes                      | Number of "Likes" Level Has                   |
| Boos                       | Number of "Boos" Level Has                    |
| Unique_Players_And_Versus  | Number of Unique Players including Versus     |
| Weekly_Likes               | Number of Weekly Likes Level Received         |
| Weekly_Plays               | Number of Weekly Plays Level Receivd          |

# Changelog

Version 1.0 - Uploaded Files
