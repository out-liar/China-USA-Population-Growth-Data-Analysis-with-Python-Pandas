# China-USA-Population-Growth-Data-Analysis-with-Python-Pandas
Graph 1 shows the absolute population of China and the USA. Graph 2 shows the % population growth of China and the USA.

import pandas as pd
from matplotlib import pyplot as plt
data = pd.read_csv('countries.csv')


data

# This will display the data frame.

# To compare the population growth in the US & China,
#  the first step is to isolate the data of each.

us = data[data.country == 'United States']

china = data[data.country == 'China']

us
china



# GRAPH 1
# Plotting the data:
plt.plot(china.year, china.population / 10**6, color='r')
plt.plot(us.year, us.population / 10**6, color='b')


# Formatting Graph 1:
plt.legend(['China', 'USA'])
plt.xlabel('Year', fontsize=16)
plt.ylabel('Population in millions', fontsize=16)
plt.title('Absolute Population of China & the USA', fontsize=16, color='g')
plt.show()




# GRAPH 2
us.population

us.population / us.population.iloc[0] * 100

# Now the first year is set to 1, and everything is is relative to it,
#  as a percentage.

# Plotting the data:
plt.plot(china.year, china.population / china.population.iloc[0] *100, color='r')
plt.plot(us.year, us.population / us.population.iloc[0] *100, color='b')

# Plotting Graph 2:
plt.legend(['China', 'USA'])
plt.xlabel('Year', fontsize=16)
plt.ylabel('Population Growth (First year = 100%)', fontsize=11)
plt.title('% Growth in Population of China & the USA)', fontsize=15, color='g')
plt.show()







