# BudgetBuddy App

BudgetBuddy is an Android application designed to help users track their income, expenses, and financial goals. It provides a simple and interactive interface to add transactions, set financial goals, and monitor progress through visual summaries and a progress bar.  

---

## Features

- **User Authentication**: Displays logged-in user email.
- **Add Transactions**: Record income and expenses with descriptions and amounts.
- **Set Financial Goals**: Set minimum and maximum financial goals.
- **Real-Time Summary**: Automatically calculates total income, expenses, and balance.
- **Progress Visualization**: Shows goal completion using a progress bar.
- **Custom Notifications**: Alerts users when a transaction is added or goals are updated.
- **Settings**: Placeholder for app settings and preferences.
- **Demo API Integration**: Example calls to fetch and add users using Retrofit (optional).

---

## Project Structure
```plaintext
BudgetBuddy/
├── app/
│ ├── src/
│ │ ├── main/
│ │ │ ├── java/com/example/budgetbuddy_poe/
│ │ │ │ ├── MainActivity.kt # Main dashboard with summary, progress, and notifications
│ │ │ │ ├── AddTransactionActivity.kt # Activity to add income or expense
│ │ │ │ ├── SetGoalsActivity.kt # Activity to set min and max financial goals
│ │ │ │ ├── TransactionAdapter.kt # RecyclerView adapter for transaction list
│ │ │ │ ├── Transaction.kt # Data class representing a transaction
│ │ │ │ ├── User.kt # Data class representing a user (for API)
│ │ │ │ └── RetrofitClient.kt # API client using Retrofit (optional)
│ │ │ ├── res/
│ │ │ │ ├── layout/
│ │ │ │ │ ├── activity_main.xml
│ │ │ │ │ ├── activity_add_transaction.xml
│ │ │ │ │ ├── activity_set_goals.xml
│ │ │ │ │ └── notification_layout.xml
│ │ │ │ ├── values/
│ │ │ │ │ ├── colors.xml
│ │ │ │ │ ├── strings.xml
│ │ │ │ │ └── styles.xml
│ │ │ │ └── drawable/
│ │ │ │ └── notification_background.xml
│ │ │ └── AndroidManifest.xml
│ └── build.gradle
├── build.gradle
└── README.md
```

---

## Installation

1. Clone the repository:  

https://github.com/MrPREDDY18/BudgetBuddy-POE_PART3.git

2. Open the project in Android Studio.

3. Build and run the project on an Android emulator or physical device (minimum SDK: 21).


## Usage

1. Launch the app.

2. Logged-in user email will be displayed.

3. Add a transaction by clicking Add Transaction and fill in the details.

4. Set financial goals via Set Goals.

5. Monitor income, expenses, balance, and progress towards goals.

6. Notifications will appear when transactions or goals are updated.

## Code Examples

### Add Transaction Result Handling

val finalAmount = if (type == "Expense") -amount else amount
val resultIntent = Intent().apply {
    putExtra("description", description)
    putExtra("amount", finalAmount)
    putExtra("type", type)
}
setResult(Activity.RESULT_OK, resultIntent)
finish()


### Updating Summary

val income = transactions.filter { it.type == "Income" }.sumOf { it.amount }
val expenses = transactions.filter { it.type == "Expense" }.sumOf { it.amount }
val balance = income + expenses

tvIncome.text = "Income: R${"%.2f".format(income)}"
tvExpenses.text = "Expenses: R${"%.2f".format(expenses)}"
tvBalance.text = "Balance: R${"%.2f".format(balance)}"


## Dependencies

- Kotlin
- AndroidX Libraries (RecyclerView, AppCompat)
- Retrofit2 (for API calls, optional)

  ## Contributing

- Contributions are welcome!

- Fork the repository.

- Create a feature branch (git checkout -b feature-name).

- Commit your changes (git commit -m 'Add feature').

- Push to the branch (git push origin feature-name).

- Create a Pull Request.

## Youtube Link 
https://youtube.com/shorts/54xMLKZy5Ss?feature=share   
