# REAL TIME BIDDING (RTB)

1. GENERAL INFORMATION
   Real-Time Bidding (RTB) is an advanced method in digital advertising that allows advertisers to bid for ad impressions
   in real-time, as a user is loading a webpage or app. It has revolutionized the display advertising industry by making
   it more efficient, transparent, and personalized.

How RTB Works:

- Ad Exchange: Acts as a marketplace where ad spaces (impressions) from publishers are auctioned. It collects details
  about each available ad slot (e.g., size, URL, audience data like IP address, cookie ID, or iOS IDFA) and sends a bid
  request to multiple DSPs.
- Demand Side Platform (DSP): Represents advertisers in the auction. When a DSP receives a bid request, it:
  - Evaluates the Request: Checks if the ad slot and audience match an advertiser's targeting criteria.
  - Decides to Bid or Not: If there's a match, the DSP participates in the auction.
  - Sets the Bid Price: Using algorithms, it determines the optimal price for the ad impression and sends a bid response
    back to the Ad Exchange.
- Auction: The Ad Exchange runs an auction using the bids from all participating DSPs. The highest bidder wins, and
  their ad is displayed to the user.

Key Terms:

- Ad Impression: A single instance of an ad being displayed to a user.
- Ad Exchange: A digital marketplace where ad impressions are bought and sold.
- Demand Side Platform (DSP): A platform used by advertisers to bid for and purchase ad impressions in real-time.
- Bid Request: Information sent by the Ad Exchange to DSPs about an ad slot, including size, audience data, and more.
- Bid Response: The DSP's reply to a bid request, including the bid price and ad creative if participating.
- Auction: The process where the Ad Exchange determines the winner among all bid responses.
- Impression event: The display of an ad to a user on a webpage or app.
- Click event: The action taken by a user when they interact with an ad by selecting it.
- Conversion event: A desired action completed by the user after interacting with the ad, such as making a purchase or
  signing up.

The primary goal of RTB is to maximize advertiser outcomes (e.g., clicks, conversions) while staying within a fixed
budget. DSP algorithms play a crucial role by analyzing vast amounts of data in real-time to bid effectively, ensuring
advertisers achieve the best return on investment (ROI).

# The Problem Statement

In the first part of the problem, we were tasked with determining whether or not to participate in the Auction's bidding process, given all the information about the user and the platform. The second part of the task involved predicting and returning an optimal bidding price, based on our chances of getting a click/conversion after an impression event.

# Our Approach

The first part was a classification task with our target variables:
1) 'is_clk' representing whether the impression would result in a click, given the impression event.
2) 'is_conv' representing whether the impression would result in a conversion, given the impression event.

We tried two models for this: LightGBM and ANNs, and the results of those models along with the model architectures are displayed in this repository.

The second part was to return the optimal bidding price, if either of the predictions from the first part turned out to be true.
We tried an XGBRegressor for this task. The results are displayed in this repository.
