# telo

**

**
class BankingFeeCalculator:
    def __init__(self, transaction_fee_rate, minimum_balance):
        self.transaction_fee_rate = transaction_fee_rate
        self.minimum_balance = minimum_balance

    def calculate_transaction_fee(self, amount):
        fee = amount * self.transaction_fee_rate
        return fee

    def calculate_minimum_balance_fee(self, current_balance):
        if current_balance < self.minimum_balance:
            fee = self.minimum_balance - current_balance
            return fee
        else:
            return 0

if __name__ == "__main__":
    transaction_fee_rate = 0.02  # Transaction fee rate of 2%
    minimum_balance = 1000  # Minimum balance required
    balance = 1500  # Current balance in the account
    amount_transacted = 500  # Amount being transacted

    calculator = BankingFeeCalculator(transaction_fee_rate, minimum_balance)

    transaction_fee = calculator.calculate_transaction_fee(amount_transacted)
    minimum_balance_fee = calculator.calculate_minimum_balance_fee(balance)

    total_fee = transaction_fee + minimum_balance_fee

    print("Transaction Fee: ${:.2f}".format(transaction_fee))
    print("Minimum Balance Fee: ${:.2f}".format(minimum_balance_fee))
    print("Total Fee: ${:.2f}".format(total_fee))
