# CLI Expense Tracker (Rust Starter)

A beginner-friendly command-line expense tracker written in Rust. This repository serves as a starter template for a hands-on Rust workshop or coding challenge.

---

## 🚀 Getting Started

### Prerequisites

Ensure you have Rust and Cargo installed on your system. If you do not have Rust installed, download it via [rustup.rs](https://rustup.rs/):

```bash
# Verify installation
cargo --version
rustc --version
```

### Running the Project

Clone or open this repository, navigate to the project root directory, and run:

```bash
cargo run
```

Cargo will automatically compile and run the application.

To check for compilation errors without building the binary:

```bash
cargo check
```

---

## 📂 Project Structure

```text
.
├── Cargo.toml      # Project manifest and package metadata
├── README.md       # Project guide and challenges
└── src
    └── main.rs     # Main entry point, Expense struct, and interactive CLI loop
```

### Current Features
- **`Expense` Struct**: Models an individual expense with `description` (`String`) and `amount` (`f64`).
- **In-Memory Storage**: Stores expenses in a dynamic `Vec<Expense>`.
- **Interactive Command Loop**: Allows users to add expenses and list currently recorded expenses.

---

## 🛠️ Workshop Issues & Challenges

Participants are tasked with implementing the following three features in [src/main.rs](file:///c:/Code%20Arena/CLI%20Expense%20Tracker/src/main.rs):

### 📌 Issue 1: Calculate Total Sum of Expenses
- **Goal**: Write a function that iterates through the `Vec<Expense>` and calculates the total sum of all recorded expenses.
- **Requirements**:
  - Implement a helper function, e.g., `fn calculate_total(expenses: &[Expense]) -> f64`.
  - Format and print the total sum to two decimal places (e.g., `Total Expenses: $124.50`).
  - Connect this function to Option `3` in the command menu.
- **Tip**: You can use a standard `for` loop or Rust's iterator combinators like `.iter().map(...).sum()`.

---

### 📌 Issue 2: Filter Expenses by Threshold Amount
- **Goal**: Allow users to filter and view only expenses that exceed a user-specified dollar amount.
- **Requirements**:
  - Prompt the user to input a minimum threshold amount (e.g., `Show expenses greater than: $`).
  - Validate and parse the threshold as an `f64`.
  - Iterate through the vector and display only expenses where `expense.amount > threshold`.
  - Display a helpful message if no expenses match the threshold.
  - Connect this functionality to Option `4` in the command menu.

---

### 📌 Issue 3: Save Expenses to a CSV File
- **Goal**: Add basic file I/O to persist the list of expenses into a `.csv` file before the program terminates.
- **Requirements**:
  - Write a function that creates or overwrites `expenses.csv` in the root directory.
  - Write a CSV header line: `description,amount`.
  - Write each expense from the vector as a row: `<description>,<amount>`.
  - Trigger this function under Option `5` before exiting the program.
  - Handle potential I/O errors gracefully (e.g., using `std::fs::File`, `std::io::Write`, or `std::fs::write`).
