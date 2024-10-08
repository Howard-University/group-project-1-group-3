
import pandas as pd
import numpy as np
df = pd.read_csv('fish_data.csv')
print(df)


# # Hailey Burnette's Work

types_of_species = df['species'].unique()
list_of_species_in_dataset = list(types_of_species)
print(list_of_species_in_dataset)


### Finding the Mean length of the dataset using Numpy:

mean_length = np.mean(df['length'])
print(mean_length)


### Finding the Mean weight ratio of the dataset using Numpy:

mean_weight = np.mean(df['weight'])
print(mean_weight)


### Finding the Mean of the weight:length ratio of the dataset using Numpy:
mean_w_l_ratio = np.mean(df['w_l_ratio'])
print(mean_w_l_ratio)


### Finding the Median of the length of the dataset using Numpy:

median_length = np.median(df['length'])
print(median_length)


### Finding the Median of the weight of the dataset using Numpy:

median_weight = np.median(df['weight'])
print(median_weight)


### Finding the Median of the weight:length ratio of the dataset using Numpy:

median_w_l_ratio = np.median(df['w_l_ratio'])
print(median_w_l_ratio)


### Finding the Standard Deviation of the length of the dataset using Numpy:

std_length = np.std(df['length'])
print(std_length)


### Finding the  Standard Deviation of the weight of the dataset using Numpy:

std_weight = np.std(df['weight'])
print(std_weight)


### Finding the Standard Deviation of the weight:length ratio of the dataset using Numpy:

std_w_l_ratio = np.std(df['weight'])
print(std_w_l_ratio)


### Finding the mean, median, mode and range of the weight:length ratio of the dataset using Basic Operations:

mean_w_l_ratio=df['w_l_ratio'].mean()
print(f'The mean length is: {mean_w_l_ratio}.')

median_w_l_ratio=df['w_l_ratio'].median()
print(f'The median length is: {median_w_l_ratio}.')

mode_w_l_ratio=df['w_l_ratio'].mode()
print(f'The median length is: {mode_w_l_ratio}.')

range_w_l_ratio = df['w_l_ratio'].max() - df['w_l_ratio'].min()
print(f'The range of the weight length ratio is: {range_w_l_ratio}.')


# ### Finding the mean, median, mode and range of the length of the dataset using Basic Operations:

meanlength=df['length'].mean()
print(f'The mean length is: {meanlength}.')

medianlength=df['length'].median()
print(f'The median length is: {medianlength}.')

modelength=df['length'].mode()
print(f'The mode length is: {modelength}.')

rangelength = df['length'].max() - df['length'].min()
print(f'The range of weight is: {rangelength}.')


### Finding the mean, median, mode and range of the weight of the dataset using Basic Operations:

meanweight=df['weight'].mean()
print(f'The mean weight is: {meanweight}.')

medianweight=df['weight'].median()
print(f'The median weight is: {medianweight}.')

modeweight=df['weight'].mode()
print(f'The mode weight is: {modeweight}.')

rangeweight = df['weight'].max() - df['weight'].min()
print(f'The range of weight is: {rangeweight}.')

### Finding the mean weight per species to indentify the heaviest and lightest fish of the dataset:

mean_weight_per_species = df.groupby('species')['weight'].mean()
print(mean_weight_per_species)


# ### Finding the mean weight:length ratio per species to indentify the skinniest and stoutest fish of the dataset:

mean_w_l_ratio_per_species = df.groupby('species')['w_l_ratio'].mean()
print(mean_w_l_ratio_per_species)

### Finding the mean length per species to identify the longest and shortest fish of the dataset:

mean_length_per_species = df.groupby('species')['length'].mean()
print(mean_length_per_species)

median_length_per_species = df.groupby('species')['length'].median()
print(median_length_per_species)


### Data visualization:


import matplotlib.pyplot as plt

mean_weight_per_species = df.groupby('species')['weight'].mean().reset_index()

plt.bar(mean_weight_per_species['species'], mean_weight_per_species['weight'], edgecolor='black')
plt.xticks(rotation=90)
plt.xlabel('Species')
plt.ylabel('Average Weight in Grams')
plt.title('Average Weight per Fish Species')
plt.show()


mean_length_per_species = df.groupby('species')['length'].mean().reset_index()

plt.bar(mean_length_per_species['species'], mean_length_per_species['length'], edgecolor='black')
plt.xticks(rotation=90)
plt.xlabel('Species')
plt.ylabel('Average Length in Centimeters')
plt.title('Average Length per Fish Species')
plt.show()

mean_weight_length_ratio_per_species = df.groupby('species')['w_l_ratio'].mean().reset_index()

plt.bar(mean_weight_length_ratio_per_species['species'], mean_weight_length_ratio_per_species['w_l_ratio'], edgecolor='black')
plt.xticks(rotation=90)
plt.xlabel('Species')
plt.ylabel('Average Weight:Length Ratio')
plt.title('Average Weight:Length Ratio per Fish Species')
plt.show()

# Short report on the findings of the data:
Mean of length: 17.35 cm
Mean of weight: 3.79 g
Mean of l : w ratio: 0.25
Largest fish by length: Sillaginopsis panijus at 31.07 cm
Smallest fish by length: Anabas testudineus at 8.18 cm
Largest fish by weight: Sillaginopsis panijus at 6.14 g
Smallest fish by weight: Puntius lateristriga at 2.63 g
Largest fish by l : w ratio: Pethia conchonius at 0.49
Smallest fish by l : w ratio: Coilia dussumieri at 0.11

import numpy as np
import pandas as pd
df =pd.read_csv('fish_data.csv')
print(df)
missing_values = df[['species', 'length','weight','w_l_ratio']]
print(missing_values)
missing_values = df.isnull().sum()
print(missing_values)

