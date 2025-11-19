class BankAccount:
    def __init__(self, account_number, holder_name, balance=0.0):
        self.account_number = account_number
        self.holder_name = holder_name
        self.balance = balance
        self.transaction_history = []

    def deposit(self, amount):
        if amount > 0:
            self.balance += amount
            self.transaction_history.append(f"Deposited ₹{amount}")
            print(f"₹{amount} deposited successfully.")
        else:
            print("Deposit amount must be positive.")

    def withdraw(self, amount):
        if 0 < amount <= self.balance:
            self.balance -= amount
            self.transaction_history.append(f"Withdrew ₹{amount}")
            print(f"₹{amount} withdrawn successfully.")
        else:
            print("Insufficient balance or invalid amount.")

    def check_balance(self):
        print(f"Available balance: ₹{self.balance}")

    def show_transactions(self):
        print("\nTransaction History:")
        for txn in self.transaction_history:
            print(" -", txn)
def main():
    print("Welcome to STATE BANK OF INDIA")
    acc_num = input("Enter Account Number: ")
    name = input("Enter Account Holder Name: ")
    account = BankAccount(acc_num, name)

    while True:
        print("\n---- MENU ----")
        print("1. Deposit")
        print("2. Withdraw")
        print("3. Check Balance")
        print("4. View Transaction History")
        print("5. Exit")

        choice = input("Enter your choice: ")

        if choice == '1':
            amt = float(input("Enter amount to deposit: "))
            account.deposit(amt)
        elif choice == '2':
            amt = float(input("Enter amount to withdraw: "))
            account.withdraw(amt)
        elif choice == '3':
            account.check_balance()
        elif choice == '4':
            account.show_transactions()
        elif choice == '5':
            print("Existing The Banking System. Goodbye!")
            break
        else:
            print("Invalid choice! Please select a valid option.")
if __name__ == "__main__":
    main()
