
import pandas as pd

# Read data
df = pd.read_excel("table_voiceID.xlsx")

# -------------------
# Voice ID 1
# -------------------
voice1_df = df[df["1"] == True]

voice1_result = (
    voice1_df
    .groupby("Date", as_index=False)["recored"]
    .sum()
)

print("Voice ID 1")
print(voice1_result)

# -------------------
# Voice ID 2
# -------------------
voice2_df = df[df["2"] == True]

voice2_result = (
    voice2_df
    .groupby("Date", as_index=False)["recored"]
    .sum()
)

print("Voice ID 2")
print(voice2_result)

# -------------------
# Voice ID 3
# -------------------
voice3_df = df[df["3"] == True]

voice3_result = (
    voice3_df
    .groupby("Date", as_index=False)["recored"]
    .sum()
)

print("Voice ID 3")
print(voice3_result)


voice1_df = df[df["1"] == True]


voice1_result = (
    voice1_df
    .groupby("Date", as_index=False)["recored"]
    .sum()
)


final_output = pd.DataFrame({
    "Jan": [
        voice1_result.loc[voice1_result["Date"]=="Jan","recored"].iloc[0],
        voice2_result.loc[voice2_result["Date"]=="Jan","recored"].iloc[0],
        voice3_result.loc[voice3_result["Date"]=="Jan","recored"].iloc[0]
    ],
    "feb": [
        voice1_result.loc[voice1_result["Date"]=="feb","recored"].iloc[0],
        voice2_result.loc[voice2_result["Date"]=="feb","recored"].iloc[0],
        voice3_result.loc[voice3_result["Date"]=="feb","recored"].iloc[0]
    ]
})

final_output.index = [1, 2, 3]

print(final_output)

