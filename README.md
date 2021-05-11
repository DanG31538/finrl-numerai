# finrl-numerai

*Below was taken directly from Numerai Tournament Documentation on 5/11/21 (https://docs.numer.ai/tournament/learn)*

<h2>Introduction</h2>
The Numerai Tournament is where you build machine learning models on abstract financial data to predict the stock market. Your models can be staked with the NMR cryptocurrency to earn rewards based on performance.

The staked models of Numerai are combined to form the Meta Model which controls the capital of the Numerai hedge fund across the global stock market.

<h2>Summary</h2>
1. Sign up at https://numer.ai/

2. Download the dataset with training data and example scripts

3. Build your model and submit your predictions back to Numerai

4. Stake NMR on your models to earn/burn based on performance

5. Automate your weekly submissions and grow your stake over time

<h2>Data</h2>
At the core of the Numerai Tournament is the free dataset. It is made of high quality financial data that has been cleaned and regularized and obfuscated.

Each id corresponds to a stock at a specific time era. The features describe the various quantitative attributes of the stock at the time. The target represents an abstract measure of performance ~4 weeks into the future.

<h2>Modeling</h2>
Your objective is to build a model to predict the future target using live features that correspond to the current stock market.

You can use any language or framework to build your model.

<h2>Submissions</h2>
Every Saturday at 18:00 UTC a new round opens and new tournament data is released. To participate in the round, you must submit your latest predictions by the deadline on Monday 14:30 UTC.

*Note: You must submit predictions every week to participate in the Numerai Tournament.*

Options:

1. Download the latest dataset and submit your predictions manually using the website.

2. Connect directly to our GraphQL API or via the official Python and R api clients.

3. Deploy your trained model to the cloud and automate your entire weekly submission workflow with the Numerai Compute framework

<h2>Diagnostics</h2>
Upon each submission, we will show you diagnostic metrics to help you understand the performance and risk characteristics of your model over the historical validation eras. 

*Note: Using this historical evaluation tool repeatedly will quickly lead to overfitting. Treat diagnostics only as a final check in your model research process.*

<h2>Scoring</h2>
You are primarily scored on the correlation (corr) between your predictions and the targets. The higher the correlation the better.

You are also scored on your meta model contribution (mmc) and feature neutral correlation (fnc). The higher the meta model contribution and feature neutral correlation the better.

Each submission will be scored over the ~4 week duration of the round. Submissions will receive its first score starting on the Thursday after the Monday deadline and final score on Wednesday 4 weeks later for a total of 20 scores.

Since a round takes ~4 weeks to resolve, if you submit new predictions every week, you will receive multiple (up to 4) overlapping scores on each scoring day from the 4 ongoing rounds. Your model's live scores can be viewed publicly on its model profile page. You can also zoom in to a specific round and see the 20 daily scores within the round.

<h2>Staking</h2>
You can optionally stake NMR on your model to earn or burn based on your corr and/or mmc scores. You cannot stake on your fnc scores.

Staking means locking up NMR in a smart contract on the Ethereum blockchain. For the duration of the stake, Numerai is given the permission to add payouts to or burn from the NMR locked up.

You can manage your stake on the website. When you increase your stake, NMR is transferred from your wallet to the staking contract. When you decrease your stake, NMR is transferred from the staking contract back into your wallet after a ~4 week delay. You can also change your stake type, which determines which scores (corr and/or mmc) you want to stake on.

<h2>Payouts</h2>
Payouts are a function of your stake value and scores. The higher your stake value and the higher your scores, the more you will earn. If you have a negative score, then a portion of your stake will be burned. Payouts are limited to ±25% of the stake value per round.

The stake_value is the value of your stake on the first Thursday (scoring day) of the round.

The payout_factor is number that scales with the total NMR staked across all models in the tournament. The higher the total NMR staked above the 300K threshold the lower the payout factor.

The corr_multiplier and mmc_multiplier are configured by you to control your exposure to each score. You are given the following multiplier options.

*Note: The payout factor curve and available multiplier options may and will be updated by Numerai in the future alongside major tournament releases.*

With every daily score, a new daily update on your payout is also computed. These daily payouts are also just updates and only the final payout of a round counts. You can track your daily payouts with the community-built Numerai Payouts app.

Final payouts are paid into your stake at the end of the round (Wednesday). When you start staking, your stake value will remain constant for the first 4 rounds. Afterwards, your stake value will update every week based on your payout of the round 4 weeks ago.

Your stake value will grow as long as you continue to have positive scores. Here are some example payout projections assuming that the model gets the same positive scores every week for 52 weeks.

<h2>Leaderboard</h2>
The leaderboard can be sorted by the reputation of model's corr, mmc, and fnc. Reputation is the weighted average of a given metric over the past 20 rounds.

Keep an eye on the leaderboard to see how your models compare to all other models in terms of performance and returns from staking.
