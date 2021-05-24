```function main() {
  Logger.log("Budget-Bid input mistake checker");
  Logger.log("=========================");
  budgetDigitChecker();
  Logger.log("=========================");
  adGroupBidChecker();
}

function budgetDigitChecker() {
  var campaignIterator = AdsApp.campaigns()
    .withCondition("Status = ENABLED")
    .get();
  Logger.log("Budget found > €100");
  while (campaignIterator.hasNext()) {
    var campaign = campaignIterator.next();
    var campaignName = campaign.getName();
    var budget = campaign.getBudget();
    var budgetCampaignIterator = budget.campaigns().get();
    var budgetAmount = budget.getAmount();
    if (budgetAmount > 99) {  
       Logger.log("...........................");
       Logger.log(campaignName);
       Logger.log(budgetAmount);
    }
  }
}

function adGroupBidChecker() {
  var adGroupIterator = AdsApp.adGroups()
    .withCondition("CampaignStatus = ENABLED")
    .withCondition("Status = ENABLED")
    .get();
  Logger.log("Ad group bidding found > €1.00");
  while (adGroupIterator.hasNext()) {
    var adGroup = adGroupIterator.next();
    var adGroupName = adGroup.getName();
    var adGroupCpc = adGroup.bidding().getCpc();
    if (adGroupCpc > 1) {
      Logger.log("...........................");
      Logger.log(adGroupName);
      Logger.log(adGroupCpc);  
    }
    
  }
}
