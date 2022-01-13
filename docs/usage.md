# Usage

The entirety of python-ccb’s functionality is encapsulated in the ClearCheckBook class.

## Getting started

ClearCheBook class accepts three parameters:

 - `username` (required) Username used to login to ClearCheckBook.
 - `password` (required) Password used to login to ClearCheckBook.
 - `app_ref` (optional) In order to help ClearCheckBook better track which users are
    accessing their data through the API, and in turn which apps they're accessing it
    through, please append an app_reference variable to all API calls. Defaults to `ccb`.

The simplest use case is getting all transactions:
```python
import ccb

session = ccb.ClearCheckBook('user', 'passwd')
for transaction in session.get_transactions():
    print(transaction)

```
[`get_transactions`](reference.md#ccb.ClearCheckBook.get_transaction) is an iterator
that gets all transactions. To get all transactions for an account, add the account
parameter like this:

```python
import ccb

session = ccb.ClearCheckBook('user', 'passwd')
account = session.get_account('My Account')
for transaction in session.get_transactions(account=account):
    print(f'Transaction: {transaction.description}, amount: {transaction.amount}')

```

[`Transaction`](reference.md#ccb.Transaction) objects represents a transaction from 
ClearCheckBook. All the propierties are documented in the [Reference](reference.md) page

### Insert a transaction

Inserting a transaction is fairly simple too:

```python
import ccb

session = ccb.ClearCheckBook('user', 'passwd')
account = session.get_account('My Account')
category = session.get_account('My Category')
new_tran = ccb.Transaction('Description', 50, account, category)
new_tran = session.insert_transaction(new_tran)

print(f'Transaction ID: {new_ran.id}'
```

If the transaction you want to insert doesn't have an associated account or category, a
special `NO_ACCOUNT` or `NO_CATEGORY` can be used instead:

```python
import ccb

session = ccb.ClearCheckBook('user', 'passwd')
new_tran = ccb.Transaction('Description', 50, ccb.NO_ACCOUNT, CCB.NO_CATEGORY)
new_tran = session.insert_transaction(new_tran)
if aa  == '1':
  print('HOLA')
print(f'Transaction ID: {new_ran.id}'
```

### Modify a transaction

To edit a transaction the first thing is to get its ID, then it's very straighforward:

```python
import ccb

session = ccb.ClearCheckBook('user', 'passwd')

for transaction in session.get_transactions():
    if transaction.description == 'Thing I'm Looking For':
      break

transaction.description = 'I Found What I Was Looking For'
session.edit_transaction(transaction)
```
