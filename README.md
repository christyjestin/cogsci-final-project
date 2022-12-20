# cogsci-final-project

Please find a repository of all code written for our research projec. Here's a breakdown of all the files included:

### Data

**data.csv** is a csv containing all unprocessed data returned by our Qualtrics survey.

**likelihood_data.csv** and **posterior_data.csv** contain postprocessed data split by the likelihood (behavior|intent) version and the posterior (intent|behavior) version of the survey. Both csvs are organized with each row containing the responses of one survey participant, with distribution valued normalized. This means that within **likelihood_data.csv**, all P(action|_intention_) values across each intention of _Friendship, Relationship, Hookup_ are normalized to a distribution summing to 1, while within **posterior_data.csv**, all P(intention, _action_) values acress each potential action (potential text messages you receive) are normalized to a distribtion. All data processing and normalization was done in **process.ipynb**. All rows are anonymized, with demographics of each respondent stored as defined by demographic keys define in **process.ipynb**.

### Code

As mentioned, **process.ipynb** contains all code used to process, normalize, and rekey the raw data before analysis could be performed. **visualization.ipynb** contains all code and graphs for visualizing the results of our data, including full plots of the likelihood and the posterior across each intention/action, and individual likelihood/posterior plots broken down by demographic. **calculation.ipynb** contains code written to develop our model to compute priors. We did this by computing the average likelihood and posterior distributions and performed a grid search to check possible values for the prior distribution. We considered generated models by combining the average likelihood distribution and the generated prior, and comparing to the average posterior with KL divergence as our distance function. The prior values with the lowest KL divergence became our optimal prior.
