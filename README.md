# EXEMPLO-ETL
EXEMPLO ETL - CONSTRUÍDO A PARTIR DO GOOGLE COLAB (BI)


# Importando a biblioteca pandas
import pandas as pd

# Extração dos dados da filial 1 (CSV)
vendas_filial1 = pd.read_csv('vendas_filial1.csv')

# Extração dos dados da filial 2 (Excel)
vendas_filial2 = pd.read_excel('vendas_filial2.xlsx')

# Transformações 
# Podemos fazer transformações adicionais aqui, se necessário

# Visualização dos dados
print("Dados da filial 1:")
print(vendas_filial1.head())
print("\nDados da filial 2:")
print(vendas_filial2.head())





#Transformação dos dados: Calcular o valor total de vendas para cada filial
vendas_filial1['Valor Total']= vendas_filial1['Quantidade Vendida'] * vendas_filial1['Preço Unitário']
vendas_filial2['Valor Total']= vendas_filial2['Quantidade Vendida'] * vendas_filial2['Preço Unitário']

#Visualizar os dados transformados
print("Dados Transformados da Filial 1:")
print(vendas_filial1.head())
print("\nDados Transformados da Filial 2:")
print(vendas_filial2.head())





#Carregamento dos dados transformados para um arquivo CSV
vendas_filial1.to_csv('vendas_filial1_transformadas.csv', index=False)
vendas_filial2.to_csv('vendas_filial2_transformadas.csv', index=False)

#Apresentar os dados carregados dos arquivos CSV
dados_filial1 = pd.read_csv('vendas_filial1_transformadas.csv')
dados_filial2 = pd.read_csv('vendas_filial2_transformadas.csv')

print("Dados Transformados da Filial 1 (do arquivo CSV):")
print(dados_filial1.head())
print("\nDados Transformados da Filial 2 (do arquivo CSV):")
print(dados_filial2.head())


https://colab.research.google.com/drive/1f7vUTDzA4nqtjzpBajTMmlotOXyEmr8l#scrollTo=IvuqC0f2UE4J&line=1&uniqifier=1


