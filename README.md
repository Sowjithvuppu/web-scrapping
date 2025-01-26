# web-scrapping
!pip install numpy !pip install pandas !pip install bs4

import pandas as pd import requests from bs4 import BeautifulSoup

url="https://timely-sunshine-e821b3.netlify.app/"
soup=BeautifulSoup(responce.content,'html.parser')

content = soup.find('div', attrs={'class' : 'name'}) text=content.text.strip() text

data=text.split(' ') for i in data: print(i.strip())

del data[2] del data[9] data

maindata=[] for i in data: maindata.append(i.strip().split(' ')) maindata products=[] for i in maindata: for j in i: if j!='' and j.strip()!='Lowest Price' and j.strip()!='Additional Coupon Discount': products.append(j) products products=[] for i in maindata: for j in i: if j!='' and j.strip()!='Lowest Price' and j.strip()!='Additional Coupon Discount': products.append(j) products

product_names=products[::4] offer_price=products[1::4] original_price=products[2::4] discount=products[3::4]

print(product_names) print(offer_price) print(original_price) print(discount)

min_len = min(len(product_names), len(offer_price), len(original_price), len(discount))

product_names = product_names[:min_len] offer_price = offer_price[:min_len] original_price = original_price[:min_len] discount = discount[:min_len]

df = pd.DataFrame({'Product Names': product_names, 'Offer_price': offer_price, 'Original_price': original_price, 'Discount': discount}) df

df.to_csv('Products data.csv') from google.colab import files files.download('Products data.csv')
