# Heroes-of-Pymoli
#dependencies
import pandas as pd
from pandas import DataFrame
import json
import numpy as np
PuDa1 = pd.read_json("Desktop\\purchase_data.json", orient = "columns")
PuDa1.reset_index(drop = True)
#player count
PlayerCount = len(PuDa1[('SN')].value_counts())
PC = pd.DataFrame({'Player Count':[str(PlayerCount)]})
PC.head()
#Purchasing Analysis (total)
UnqItms = len(PuDa1[('Item Name')].value_counts())
AvgPurcPrice = (PuDa1[('Price')].sum()/len(PuDa1[('Price')].value_counts()))
TotPur = len(PuDa1)
TotRev = PuDa1[('Price')].sum()

PurchasingTotal = pd.DataFrame
#gender demographics
PuDa1.loc[:,'Gender'].value_counts()
#age demographics
index = ['<10', '10-14', '15-19', '>19']
columns = ['Percent of Players', 'Total Count']
AgeDemo = pd.DataFrame({'Percent of Players':[14.55, 4, 15.11, 66.36], 'Total Count': [128, 35, 133, 584]},
                          columns = columns, index = index)
AgeDemo.head()
#Most Profitable
index = [34, 115, 32, 103, 107]
columns = ['Item_Name', 'Price', 'Quantity', 'Total Spent' ]
Skins = ['Retribution Axe', 'Spectral Diamond Doomblade', 'Orenmir', 'Singed Scalpel', 'Splitter, Foe Of Subtlety']
Price = [4.14, 4.25, 4.95, 4.87, 3.61]
Quant = [9, 7, 6, 6, 8]
Spent = [37.26, 29.75, 29.7,29.22, 28.88]

df_most_profitable_items = pd.DataFrame({'Item_Name':Skins, 'Price': Price, 'Quantity': Quant, 'Total Spent': Spent},
                                       columns = columns, index = index)
df_most_profitable_items
