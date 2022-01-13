# Reference

::: ccb.ClearCheckBook
    rendering:
        show_root_heading: true

::: ccb.Account
    selection:
        filters: ["!^_"]
    rendering:
        show_root_heading: true
        show_source: false

::: ccb.Category
    selection:
        filters: ["!^_"]
    rendering:
        show_root_heading: true
        show_source: false

::: ccb.Currency
    selection:
        filters: ["!^_"]
    rendering:
        show_root_heading: true
        show_source: false

::: ccb.Transaction
    selection:
        filters: ["!^_"]
    rendering:
        show_root_heading: true
        show_source: false

# Account and transaction constants

The following account and transaction codes are numeric constants importable from `ccb`.

|   Constant   |      Description                                               |
|:------------ |:-------------------------------------------------------------- |
| CASH         | Cash account                                                   |
| CHECKING     | Checking account                                               |
| SAVINGS      | Savings account                                                |
| CREDIT       | Credit Card account                                            |
| INVESTMENT   | Investment account                                             |
| WITHDRAW     | Withdraw transactions                                          |
| DEPOSIT      | Deposit transactions                                           |
| TRANSFER     | Transfer transactions                                          |
| NO_ACCOUNT   | Special account for transactions without an assigned account   |
| NO_CATEGORY  | Special category for transactions without an assigned category |
