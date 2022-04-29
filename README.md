# Gapminder-Dataset:
Gerando um line plot a partir de um DataFrame (Gapminder dataset).

Os gráficos mostram a expectativa de vida no Brasil entre 1952-2007.
# Importando as bibliotecas:
import plotly.express as px
import pandas as pd  

df = px.data.gapminder()
df.head()

![image](https://user-images.githubusercontent.com/98922466/165863475-8e59b649-6950-4ce0-ad8c-02209f725043.png)

df['continent'].unique()
array(['Asia', 'Europe','Africa','Americas', 'Oceania'], dtype=object)

df['country'].unique()
array(['Afghanistan', 'Albania', 'Algeria', 'Angola', 'Argentina',
       'Australia', 'Austria', 'Bahrain', 'Bangladesh', 'Belgium',
       'Benin', 'Bolivia', 'Bosnia and Herzegovina', 'Botswana', 'Brazil',
       'Bulgaria', 'Burkina Faso', 'Burundi', 'Cambodia', 'Cameroon',
       'Canada', 'Central African Republic', 'Chad', 'Chile', 'China',
       'Colombia', 'Comoros', 'Congo, Dem. Rep.', 'Congo, Rep.',
       'Costa Rica', "Cote d'Ivoire", 'Croatia', 'Cuba', 'Czech Republic',
       'Denmark', 'Djibouti', 'Dominican Republic', 'Ecuador', 'Egypt',
       'El Salvador', 'Equatorial Guinea', 'Eritrea', 'Ethiopia',
       'Finland', 'France', 'Gabon', 'Gambia', 'Germany', 'Ghana',
       'Greece', 'Guatemala', 'Guinea', 'Guinea-Bissau', 'Haiti',
       'Honduras', 'Hong Kong, China', 'Hungary', 'Iceland', 'India',
       'Indonesia', 'Iran', 'Iraq', 'Ireland', 'Israel', 'Italy',
       'Jamaica', 'Japan', 'Jordan', 'Kenya', 'Korea, Dem. Rep.',
       'Korea, Rep.', 'Kuwait', 'Lebanon', 'Lesotho', 'Liberia', 'Libya',
       'Madagascar', 'Malawi', 'Malaysia', 'Mali', 'Mauritania',
       'Mauritius', 'Mexico', 'Mongolia', 'Montenegro', 'Morocco',
       'Mozambique', 'Myanmar', 'Namibia', 'Nepal', 'Netherlands',
       'New Zealand', 'Nicaragua', 'Niger', 'Nigeria', 'Norway', 'Oman',
       'Pakistan', 'Panama', 'Paraguay', 'Peru', 'Philippines', 'Poland',
       'Portugal', 'Puerto Rico', 'Reunion', 'Romania', 'Rwanda',
       'Sao Tome and Principe', 'Saudi Arabia', 'Senegal', 'Serbia',
       'Sierra Leone', 'Singapore', 'Slovak Republic', 'Slovenia',
       'Somalia', 'South Africa', 'Spain', 'Sri Lanka', 'Sudan',
       'Swaziland', 'Sweden', 'Switzerland', 'Syria', 'Taiwan',
       'Tanzania', 'Thailand', 'Togo', 'Trinidad and Tobago', 'Tunisia',
       'Turkey', 'Uganda', 'United Kingdom', 'United States', 'Uruguay',
       'Venezuela', 'Vietnam', 'West Bank and Gaza', 'Yemen, Rep.',
       'Zambia', 'Zimbabwe'], dtype=object)
       
  # Vizualização da expectativa de vida no Brasil:
  df = df.query('country == "Brazil"')
  
  df.head()
       
 ![image](https://user-images.githubusercontent.com/98922466/165864001-2adeb749-f39b-411f-8a3c-fd9958c8ec6b.png)
       
# Criação de um título para figura e armazenar na variável:
title = 'Expectativa de vida no Brazil (1952-2007)'

fig = px.line(df, x = 'year', y = 'lifeExp', title = title)

fig.show()

![image](https://user-images.githubusercontent.com/98922466/165864231-bbc766e1-36da-4714-872c-0df8b241204e.png)

# Vizualização da expectativa de vida no Brasil nos anos 1952-2007. Alteração do título dos eixos e mudança da cor de fundo do gráfico:
fig.update_layout(xaxis = dict(title = 'Tempo'),
                  yaxis = dict(title = 'Expectativa de vida'),
                  plot_bgcolor = 'white'
                 )

![image](https://user-images.githubusercontent.com/98922466/165864544-48e0c58a-7dec-43d1-9ca2-658f3f6e791e.png)


