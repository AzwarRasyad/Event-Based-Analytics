# Event-Based-Analytics

# Project Description

You work at a startup that sells food products. You need to find out the behavior of the company's app users.

First of all, try to study the sales funnel first. Find the path that the user must follow to reach the purchase stage. How many users actually make it to the purchase stage? How many users got stuck in the previous stages? At what stage exactly did this happen?

Then, have a look at the results of the A/A/B testing (Read on for more information about A/A/B testing). The web designer team wanted to change the font for the entire app, but the product manager was worried that users would find the new design distracting. They also decided to make a decision based on the results of A/A/B testing.

The users were divided into three groups: two control groups were shown with the old font version and one test group was shown with the latest font version. Your job is to find out which font will give you the best results.

Making two groups A (control) does provide certain advantages. We can lay down the rule that the accuracy of the test is acceptable only if the two control groups give similar results. If there is a significant difference between the two groups A, this can help us to identify factors that might be distorting our results. Comparing the control group will also give us an idea of how much time and data is needed when running the next process.

You will use the same dataset to do regular analysis and to do A/A/B analysis. In real-world projects, experiments like this are routinely performed. Analysts study app quality using common data, regardless of whether users participate in experiments or not.

# Data Description

Each log entry is a record of a user action or an event.

- `EventName` — 
- `DeviceIDHash` — User's unique ID
- `EventTimestamp` — event time
- `ExpId` — experimental numbers: 246 and 247 for the control group, 248 for the test group

# Instructions

**Step 1. Open the data file and review the general information**

File path: `/datasets/logs_exp_us.csv` 

**Step 2. Prepare data for analysis**

- Rename the column to whatever you want.
- Check for missing values and their data types. Correct the data if needed.
- Add date and time fields, as well as a separate column for dates.

**Step 3. Study and check the data**

- How many events are logged?
- How many users are logged?
- What is the average number of events per user?
- What time period does the data cover? Find the maximum and minimum dates. Construct a histogram based on date and time. Can you ensure that the data you have is complete for all periods? Past events may appear in the logs of some users for technical reasons, and this can mess up the overall data distribution. Find the moment when the data starts to feel complete and ignore the old data. Which period does the data you have actually represent?
- Did you lose a lot of events and users when you got rid of old data?
- Make sure you have users from all three experimental groups.

**Step 4. Study the funnel of events**

- See what events are in the log and how many times they occur. Sort those events by frequency.
- Find the number of users who performed each action. Sort events by number of users. Calculate the proportion of users who performed an action at least once.
- In what order do you think the actions took place? Are they all part of one sequence? You don't need to take everything into account when calculating the funnel.
- Use event funnels to find the percentage of users who persisted from one stage to the next. (For example, for the sequence of events A → B → C, calculate the ratio of users in stage B to the number of users in stage A, and the ratio of users in stage C to the number of users in stage B).
- At what stage did you lose a lot of users?
- What percentage of users successfully complete all stages, from the first event to checkout?

**Step 5. Study the results of your experiment**

- How many users are there in each group?
- We have two control groups in A/A testing, where we check our mechanics and calculations. See if there is a statistically significant difference between samples 246 and 247.
- Select the most popular events. In each control group, find the number of users who performed the action. Find the percentage. Check whether the differences between groups are statistically significant. Repeat this procedure for all other events (it will save time if you can create a custom function to perform this test). Can you confirm if the groups are properly split?
- Do the same for the group of users shown the latest font version. Compare the results with each control group for each event separately. Compare the results with the combined results for the control group. What conclusions can you draw from the experiment?
- What level of significance did you set to test the statistical hypothesis mentioned above? Count how many statistical hypothesis tests you have done. With a statistical significance level of 0.1 - one in 10 results could be wrong. What level of significance should be set? If you want to change it, just rerun the previous step and check your conclusions.
