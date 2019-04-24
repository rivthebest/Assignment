# Data Engineering - Assignment
## Introduction
In this exercise, we will build a Spark job for MarketInvoice based on track-record.
To do this, we will be using the publicly available Loan book which is split up in XML files (trades.zip). Let’s start with clarifying some of the terms.

We call the company that raises an invoices the seller. The company which the invoice is raised against is called the debtor. In the loan book, you can find the column Seller ID, which contains an id, which can be used to identify different transactions relating to the same seller.

At MarketInvoice, our transactions are called trades. Within a trade, the seller receives money (the advance) in return for one or multiple invoices. When a seller submits a trade, they will submit an Expected Payment Date.  When a trade is not being paid within the agreed terms, it is said to be delinquent or in arrears. This is the variable that we will be predicting.

## Instructions
1. Write a script in PySpark to read in the data. Ensure that you will only be working with the Trade Type “Standard”.

2. Add a couple of features to the dataset:
    - The expected duration: the number of days between advance date and expected payment date.
    - The number of previously settled trades for the seller. Make sure to only count trades where the Settlement Date is before the Advance Date of the trade.

3. Don't use any external library, but try to solve the problem with the normal functionality. Explain what would improve when using external library and give an example which library could help with this assignment.