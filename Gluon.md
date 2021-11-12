# General notes

## Payee/Payee Accounts
- Merchants are the companies we are paying. It's the same for everyone
	- A template for how to login to the merchant for everyone, not just my user
- Payee is the user's actual login for the merchant
	- Your relationship with a merchant
	- Can exist without a merchant in our directory
- Payee Account
	- Specific accounts with the merchant.  For example: Internet account & Electric account
- Gluon and NOW! API use the same resources, but they use them in different ways
- Merchants come from BiRDS, Payees and PayeeAccounts are maintained in Gluon for the user

## Payments and Funding Overview
- Payments are sent to Payee Accounts with SendOnDates
	- Fraud checks are performed on every payment
	- If FMS doesn't approve the payment, then the payments stay in processing.
	- If the user makes any changes to the payment in the future, FMS still needs to run against the change
	- Background thread looking for approved payments in PENDING with send on date for today
	- Sends payments over to paymentRouter