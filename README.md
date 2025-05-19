# Kelvin
Python Code
# Mortgage variables
outstanding_amount = 9136695.84  # Replace with the outstanding mortgage balance
remaining_months = 332       # Replace with the remaining mortgage period in months
annual_interest_rate = 2.491   # Replace with the current annual interest rate in %

# Convert annual interest rate to a monthly interest rate (decimal form)
monthly_interest_rate = annual_interest_rate / 100 / 12

# Calculate the monthly payment using the annuity formula
if monthly_interest_rate > 0:
    monthly_payment = (outstanding_amount * monthly_interest_rate * (1 + monthly_interest_rate) ** remaining_months) / \
                      ((1 + monthly_interest_rate) ** remaining_months - 1)
else:
    # If interest rate is 0, monthly payment is simply the outstanding amount divided by months
    monthly_payment = outstanding_amount / remaining_months

# Calculate the monthly interest portion for the first payment
first_month_interest = outstanding_amount * monthly_interest_rate
first_month_principal = monthly_payment - first_month_interest

# Output results
print(f"Monthly Payment: ${monthly_payment:.2f}")
print(f"First Month Interest Amount: ${first_month_interest:.2f}")
print(f"First Month Principal Amount: ${first_month_principal:.2f}")
