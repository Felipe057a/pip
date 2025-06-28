To execute properly, use the following commands for your code:
['SetPassRD', '__all__', '__builtins__', '__cached__', '__doc__', '__file__', '__loader__', '__name__', '__package__', '__path__', '__spec__', 'modulo']
Demo of use:
*-----------------------------------------------*
from passwordrd.modulo import SetPassRD

# Step 1: User sets a password
defined_password = input("Create a security password: ")

# Step 2: Create a protection object with the password
protector = SetPassRD(defined_password)

# Simulated Python code to be protected
code = input("Enter a Python expression to execute (e.g., 2 + 2): ")

# Step 3: Ask for password to authorize execution
entered_password = input("Enter the password to authorize execution: ")

# Step 4: Try to execute the code with password validation
try:
    result = protector.eval(code, line=1, caractere=1, senha=entered_password)
    print("Result:", result)
except PermissionError:
    print("❌ Incorrect password. Execution blocked.")
except RuntimeError as e:
    print("⚠️ Error executing the code:", e)

