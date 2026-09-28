# generator-parameter-monitor
# Generator Parameter Monitoring System

MIN_VOLTAGE = 200
MAX_VOLTAGE = 250
MAX_CURRENT = 100
MIN_FREQUENCY = 49
MAX_FREQUENCY = 51
MAX_TEMPERATURE = 80

print("==============================")
print("    GENERATOR PARAMETER MONITOR")
print("==============================")

voltage = float(input("Enter generator voltage (V): "))
current = float(input("Enter generator current (A): "))
frequency = float(input("Enter generator frequency (Hz): "))
temperature = float(input("Enter generator temperature (°C): "))

fault = False

print("\n--- Generator Parameters ---")
print("Voltage    :", voltage, "V")
print("Current    :", current, "A")
print("Frequency  :", frequency, "Hz")
print("Temperature:", temperature, "°C")

# Voltage check
if voltage < MIN_VOLTAGE:
    print("⚠️ Under-voltage detected")
    fault = True
elif voltage > MAX_VOLTAGE:
    print("⚠️ Over-voltage detected")
    fault = True

# Current check
if current > MAX_CURRENT:
    print("⚠️ Overcurrent detected")
    fault = True

# Frequency check
if frequency < MIN_FREQUENCY:
    print("⚠️ Under-frequency detected")
    fault = True
elif frequency > MAX_FREQUENCY:
    print("⚠️ Over-frequency detected")
    fault = True

# Temperature check
if temperature > MAX_TEMPERATURE:
    print("⚠️ High temperature detected")
    fault = True

# Final status
if fault:
    print("\n🔴 GENERATOR ALERT")
    print("⚠️ Abnormal parameter detected")
else:
    print("\n🟢 GENERATOR STATUS: NORMAL")
    print("✅ All parameters are within limits")

print("\nMonitoring completed.")
