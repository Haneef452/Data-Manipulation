import pandas as pd
import numpy as np

data = {'col1': [1, 2, 3, None, 5],
        'col2': ['A', 'B', 'C', 'D', 'E'],
        'col3': np.random.randn(5)}
df = pd.DataFrame(data)

print("Original DataFrame:")
print(df.to_string())

filtered_df = df[df['col1'] > 2]
df['col3'].fillna(df['col3'].mean(), inplace=True)

summary = df.describe()

print("\nFiltered DataFrame:")
print(filtered_df.to_string())

print("\nSummary statistics:")
print(summary)
