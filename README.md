Personal Finance Management
===========================
Personal Finance Management is a set of activities performed by the customer on its financial data for the purpose of getting clear picture of the incomes/expenses trends, as well as enabling customer to manage monthly budget and personal financial goals.

Personal Finance Management starts with **categorization** of transactions into income, expense and savings & investment categories and subcategories. Majority of transactions should be automatically categorized, allowing the customer to manage categorization manually and using user categorization rules. Each transaction has a category and optionally a subcategory assigned. Categorization scheme used within the solution is described below. 

Besides spending categories, categories enum includes values for uncatogorized and split transactions.

PFM Frontend
============
PFM frontend is a single-page application written in Angular

Basic Features 5MD
--------------

### FE-B1 List transactions (1 points)

Present a list of transactions for categorization.
For each of transactions in the list present following information:
- Transaction id
- Beneficiary name
- Transaction date
- Direction (credit or debit represented as red/green arrow icon)
- Transaction amount
- Transaction currency
- Transaction kind
- Split marker (whether transaction is a split of another transaction)
- Category (PFM category of categorized transactions)
> Note that:
> - Transaction list should be filtered by account.
> - Transaction list should be sorted by date (descending) and category (ascending).

![image](images/148_pfm_financialoverview_tree.jpg)


### FE-B2 Categorize a single transaction (1 points)
Offer option to set or change the category of transaction.
- Display drop-downs with the list of all possible PFM categories
- Display drop-downs with the list of all possible PFM subcategories filtered by category dropdown value
- Previously set category and subcategory are preselected in the dropdowns
- user can optionally select the subcategory from the list
- upon succesfull categorization (click on Apply button), category of transaction is persisted to database via API call
- newly set category is presented on the transaction list screen

![image](images/148_pfm_financialoverview_tree.jpg)

### FE-B3 Categorize multiple selected transactions (1 points)
Offer option to set or change the category of selected transactions.
- Display a button to categorize multiple transactions
- When button is clicked show a selection checkbox for each transaction
- Offer buttons to proceed with categorization or cancel selection
- When user clicks OK to proceed with categorization:
  - Display drop-downs with the list of all possible PFM categories
  - Display drop-downs with the list of all possible PFM subcategories filtered by category dropdown value
  - user can optionally select the subcategory from the list
- upon succesfull categorization (click on Apply button), categories of transactions are persisted to database via API call
- newly set categories are presented on the transaction list screen

![image](images/148_pfm_financialoverview_tree.jpg)

### FE-B4 Split transaction (2 points)
Offer option to "split transaction" from the list of transactions into multiple transactions each having a specific category and amount.
- Display two splits initialy, offer option to add additional splits
- For each split:
  - Display drop-downs with the list of all possible PFM categories
  - Display drop-downs with the list of all possible PFM subcategories filtered by category dropdown value
  - Display an input for split transaction amount
  - user can optionally select the subcategory from the list
- upon succesfull split (click on Apply button), splits are persisted via API call
- newly added splits are presented on the transaction list screen
Not that:
- Sum of amounts from split transactions must be equal to amount of original transaction.
- New transactions (resulting from split) are recorded with same attributes as the original transaction apart from category, amount and split marker.

![image](images/148_pfm_financialoverview_tree.jpg)



Extra credit features (5 points)
-----------------
### FE-A1 Present spending by category with tree map chart (1 point)
Tree map view is the chart that provides data tree in form of rectangles of various colours and sizes. Each rectangle displays information on name of category and spent amount. Size of rectangle is directly proportional to the sum value of spending transactions for the category. Only top level categories are displayed initially.
- When user clicks on a category rectangle:
  - Tree map view of subcategories related to the category is displayed
Note that:
- Chart displays information for current month but user can specify other date period

![image](images/148_pfm_financialoverview_tree.jpg)

### FE-A2 Responsive UI (2 points)
Make user interface adaptable to mobile and desktop form factor (screen width).
- All functionality must work with touch / on-screen keyboard input on mobile
- All functionality must work with mouse / keyboard input on desktop

### FE-A3 Backend simulation with sandbox in Node and Redis (2 points)
Create Node.js app using sandbox kit generator from ASEE.
Setup Redis Docker container on your machine and configure sandbox to use Redis instance as data store.
Simulate API calls according to PFM API OAS3 specification by persisting data to Redis.
Seed data from pfm-transactions.csv file.

### FE-A4 Write UI tests (2 points)
Pick a UI testing tool of you choice such as Selenium, Taiko, Puppeteer or other.
Write automated tests for A2 Categorize single transaction and A4 Split transaction requirements.

### FE-A5 Make your frontend interoperable (2 points)
Collaborate with a colleague to make your frontend work with his/her implementation of backend.
Fix any integration issues.


Above and beyond
-----------------
- Implement additional visualisations of spending by category (donut chart, pie chart, bar chart)
- Make UI visually as close as possible to designer mocks
- Be creative, surprise us!


Assumptions
------------
- You will create a Prism mock of PFM API to simulate backend calls and data.

PFM Backend
====================================
PFM microservice written in .Net core

Basic Features
--------------

### B1 Import transactions from bank file (csv) (1)
### B2 List transactions with filters and pagination
### B2 Automatically assign categories based on predefined rules
### B3 Categorize transaction
### B4 Split transaction

Advanced features
-----------------
### Ax Analytical view of spending by categories
### Ax Basic authentication
### BE-A4 Create a basic web UI (functional)
Instead
### BE-A5 Make your backend interoperable (2 points)
Collaborate with a colleague to make your frontend work with his/her implementation of backend.
Fix any integration issues.


Above and beyond
----------------

### Assumptions
- APIs you expose will conform to PFM API specifications
- 


