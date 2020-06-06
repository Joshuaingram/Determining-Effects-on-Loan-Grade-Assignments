# Determining Effects on Loan Grade Assignments

**-- Project Status: Completed**

## Project Introduction
This project was done for completion of the "Introduction to Categorical Data Analysis: class at New College of Florida in Fall 2019 (sophomore year). The motivation of this project was to determine the variables that go into determining a loan applicant's loan grade on the LendingClub platform. Understanding what variables go into determining the platform's loan grades is useful for investors to so they can evaluate the riks of loans and make adjustments to their portfolios accordingly.

### Methods Used

- Data Visualization
- Cumulative Logistic Regression

### Language

- R

## Project Description

LendingClub is a peer-to-peer lending platform that enables borrowers to have quick access to funds of up to $40,000. By partially funding loans, lenders are able to create diversiﬁed portfolios made up of any number of loans that are in accordance with their desired risk level. Lenders are able to assess the risk of each loan by accessing information ﬁlled out by the potential borrower intheapplication,aswellasadditionalinformationprovidedbyLendingClub. Onewayalender can assess risk is through the loan grades calculated and given by the LendingClub platform. 

Each loan is given a grade from A to G, A being the least risky and G being the riskiest. However, the method for loan grade selection is not explicitly stated by LendingClub. This automatically causes lenders to put trust in the platform to provide reliable and unbiased grades. Understanding some of the variables that can accurately predict loan grades gives lenders a better understanding of the grading process, as well the ability to make more informed decisions on their investments.

# The Data

A link to the original dataset used in this project can be found here: [Kaggle Dataset](https://www.kaggle.com/wendykan/lending-club-loan-data)

To better understand how loans may be graded, as well as the loans on the platform in general, the LendingClub loan dataset from kaggle.com was selected. This dataset contains information on every loan issued from 2007 to 2018 and is sourced from LendingClub itself. There are 2.26 million observations and 145 variables, as well as an accompanying data dictionary. 

The .csv ﬁle containg the loan data was 1.16 GB in size upon download and 23.84% of the values were missing. After olooking at the variables, 7 were selected for analysis. Once these were selected, our missing values were down to only .33%. Here are the variables and their descriptions, as deﬁned by the data dictionary:

***Response Variable***

- *Grade* - LendingClub assigned loan grade (A, B, C, D, E, F, G)

***Explanatory Variables***

- *Annual_Income* - the self-reported annual income provided by the borrower

- *Application_Type* - indicates whether the loan is an individual application or a joing application with two co-borrowers (Individual, Joint App)

- *Debt_to_Income* - (debt-to-income ratio) a ratio calculated using the borrower’s total monthly debt payments on the total debt obligations, excluding mortgage and the requested LendingClub loan, divided by the borrower’s self-reported income

- *Home_Ownership* - the home ownership status provided by the borrower during registration (Rent, Own, Mortgage, Own, Other)

- *Loan_Amount* - the listed amount of the loan applied for by the borrower

- *Mortgaage_Accounts* - the number of mortgage accounts the borrower has

Since limiting the amount of variables down to 7 reduced the amount of missing values by 23.51 percenatage points, it was reasonable to outright remove the remaining NA values from the data. This new data is referred to as *loans* (in italics) from this point forward. Only 8.31% of the LendingClub loans were given grades from E to G, so to make the data more interpretable and better towork with, thosegrades were combined into a new category, E-G. Finally, due to the size of the data and limited computing power, a new subset of the data called *loans.sample* was created. This subset of the data is a random sample of size 20,000 from the *loans* data. This subset of data is only used for model ﬁtting. This is because with the *loans* data, containing over 2 million observations, the ﬁt functions outputted data that was too large (over 12GB). All graphs not dealing with model ﬁts are made with the full *loans* data.

### Data Summaries

## Results

The final cumulative logistic regression model had annual income, application type, debt-to-income ratio, home ownership, loan amount, and the number of mortage accounts as the explanatory variables. Below is the ANOVA table for the model and the estimates of each explanatory variable:

Finally, see the two graphs below for the probability of a loan being assigned different loan grades by application type. The debt-to-income ratio changes, but home ownership is held at "mortgage", number of mortgage accounts at 1.56, annual income at the mean in the dataset ($78,257.95), and loan amount held at the average in the dataset ($15.125.61).

