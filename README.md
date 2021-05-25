# Google Ads Budget-Bid input checker
In this repository I deal with the common problem all marketers face when monitoring a Google Ads ad account, one of the (many) mistakes that can happen due to the human factor. Wouldn't it be great to be able to run daily a short code that checks if all budgets and bids seem "logical"? By logical I mean there has not occured any mistyping, any additional zeros in the budget or/and any wrong comma position in the bids.

A short JavaScript Google Ads script can easily help you check all values that a user has input as budget or bid and inform you if a mistake has been made.

🚸 This script is not maintained, so, in time, certain operations or even the entire script may not be functional.

Let me go through the whole process in more detail.

## What exactly does this script do

As you can understand by reading the simple code, this JS script performs three actions:
1) iterates all your ad account's enabled campaigns and checks if any of them has a daily budget > €100.
2) iterates all your ad account's enabled ad groups from all your enabled campaigns and checks if any ad group has a bid > €1.00.
3) informs you about any findings in the logs report of Google Ads UI.

## How to deploy this script

Go to the relevant gihub file in the current repository (specifically the one named "google-ad-budget-bid-input-checker--code.js") and copy the code. Go to your Google Ads ad account in Tools & Settings > Bulk actions > Scripts. Click on the "+" icon, paste the code and save your script. Try running it. The first time you do, you will have to authorize it. Proceed so (don't worry this script only reads data, it will not change/edit anything in your ad account) and you will see that the script is run and finished successfully. In the "Script history" section you will be able to see that it has been completed, as shown in the screenshot below.

<img src="https://github.com/dpan331/Google-Ads-Budget-Bid-input-checker/blob/main/img/scriptHistory.JPG" height="300" width="1100">

## How to schedule this script to run daily

In the "Scripts" section in the column "Frequency" next to your script's name, simply click on the pencil icon and set your desired frequency (i.e. "daily" at "06:00PM").

## How to check the historical output

In the "Scripts history" section, choose the desired date range and check in the "Results" column the log statements. 

<img src="https://github.com/dpan331/Google-Ads-Budget-Bid-input-checker/blob/main/img/scriptHistory_logs.JPG" height="300" width="900">

Go to your Campaigns and Ad groups views and you will be able to find which ones have wrong input.

<img src="https://github.com/dpan331/Google-Ads-Budget-Bid-input-checker/blob/main/img/campaignBudgets.JPG" height="300" width="900">

<img src="https://github.com/dpan331/Google-Ads-Budget-Bid-input-checker/blob/main/img/adGroupBids.JPG" height="300" width="900">

## Is that all?

Of course not. This is just a simple example. You can edit this script and adapt it to serve your specific case. For example:
- you can provide certain conditions for which campaigns and ad groups to check.
- you can complement the code to check on shared budgets, too.
- you can edit the code to check bids on keyword level instead of ad group level.
- you can commplement the code to send the output directly to your email.
