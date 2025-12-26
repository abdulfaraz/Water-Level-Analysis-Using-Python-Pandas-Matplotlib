import pandas as pd
import matplotlib.pyplot as plt

data = {
    "Date": [
        "2024-01-01", "2024-01-02", "2024-01-03", "2024-01-04",
        "2024-01-05", "2024-01-06", "2024-01-07", "2024-01-08",
        "2024-01-09", "2024-01-10"
    ],
    "Water_Level": [90, 85, 80, 75, 70, 65, 60, 55, 50, 45]
}
df = pd.DataFrame(data)
df["Date"] = pd.to_datetime(df["Date"])

print("Average water level:", df["Water_Level"].mean())
print("Maximum water level:", df["Water_Level"].max())
print("Minimum water level:", df["Water_Level"].min())


plt.figure(figsize=(10, 5))
plt.plot(df["Date"], df["Water_Level"], marker="o")
plt.title("Water Level in City Tank Over Time")
plt.xlabel("Date")
plt.ylabel("Water Level")
plt.grid(True)
plt.show()

refill_level = 50

print("\nRefill should be done when water level goes below", refill_level)

low_water = df[df["Water_Level"] <= refill_level]
print("\nDates when refill is needed:")
print(low_water)
