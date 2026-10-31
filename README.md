# Credit_Card_Churn_Prediction

### Predicting Which Credit Card Customers will Leave

*A data science case study: using customer history to help a bank keep the customers it already has and determine who is most likely to leave.*

**The business problem**

For a credit card issuer, every customer who closes their card account is lost revenue: the fees, interest, minimum due obligations and card spending that customer would have generated. Identifying customers who are most likely going to leave early on helps the institution control its risk exposure or create a monitoring system for customers within this category.

This model seeks to bridge the difficulty of institutions typically finding out a customer is leaving only after they have gone. By then it is too late to act. So, the question I set out to answer: Can we spot customers who are likely to leave early enough for the bank to do something about it?

**The data**

I worked with records for 10,127 credit card customers. For each one, the data shows who they are (age, gender, family size, education, marital status, income band) and how they use their card or other bank products (how long they have been a customer, how many of the bank's products they hold, how many months they were inactive, how often they contacted the bank, and how much and how often they spent).

Each customer is labelled as either still active (Existing Customer) or having closed their account (Attrited Customer). About 16% had left, so this is a real-world imbalance: most customers stay, and the ones who leave are the ones we most need to identify.

The data was clean, with no missing values. A few fields contained "Unknown" answers (for example, income or education). Rather than discard those customers, I kept "Unknown" as its own group so no one was thrown away.

**My approach, in plain terms**

1. Prepared the data so the model could learn from it, such as turning income bands into an ordered scale from lowest to highest.

2. Set aside a quarter of the customers (2,532) as an exam. The model never saw them while learning, so its results on them show how it would perform on customers it has not met.

3. Compared six different prediction methods head to head, from simple to sophisticated.

4. Chose the best performer and tried fine-tuning it. Tuning made it slightly worse, so I kept the simpler version. More complexity is not always better.

5. Saved the finished model so it can score new customers without being rebuilt.

**What the model achieved**

The two strongest methods both reached 94% overall accuracy on the exam customers. I selected the one that also did best at finding the customers who left.

Accuracy alone can flatter a model when most customers stay. A model that simply guessed "everyone stays" would be right 84% of the time while catching nobody. So here is what matters more to the business:

Of the 2,532 customers in the exam
1. Customers who actually left - 419
2. Leavers the model correctly flagged - 301 (about 7 in 10)
3. Leavers the model missed	- 118
4. Customers flagged as likely to leave	- 338
5. Of those, how many really were leaving	- 301 (about 9 in 10)
6. Loyal customers wrongly flagged - 37 (under 2% of loyal customers)

In practical terms: when the model raises a flag, it is right roughly nine times out of ten, and it catches around seven in ten of the customers who would have left. Very few loyal customers would be bothered by a needless retention offer.

**How a bank could use this**

1. Targeted retention. Each month, score the customer base and send the flagged customers a tailored offer or a call from a relationship manager to facilitate early repayment.
2. Early warning on onboarding. Score new customers early in the relationship to see who may not stay.
3. Because the flags are accurate, the retention strategy which may include creating personalized credit offers goes mostly to customers who are genuinely at risk.

**Limitations of the model**

1. About three in ten leavers still slip through. If the bank prefers to catch more of them, the model can be adjusted to do so, at the cost of more false alarms.
2. It predicts who may leave, not why. Understanding the reasons would help the bank design better offers.
3. It was tested on one snapshot of customers. Before real use it should be checked on newer data and monitored over time.

**Next steps**

This was the first of three planned uses of the same data. The next two are deciding which card type a retained customer is best suited to, and recommending a suitable credit limit. Together, the three would give a bank a single view of who to keep, what to offer them, and how much to lend.

**Skills demonstrated**

Framing a business problem as a prediction task, cleaning and preparing real customer data, avoiding misleading results by keeping a held-back test group, comparing multiple methods, judging performance by what matters to the business rather than accuracy alone, and communicating findings to a non-technical audience.
