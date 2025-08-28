# Projeto iFood Restaurants (2020–2021)

## Objetivo
Explorar dados de restaurantes do iFood (nov/2020 e fev/2021), entender tendências de crescimento, categorias mais populares e testar modelos de ML para prever `rating`.

## Bases de Dados
Os datasets originais podem ser baixados no Kaggle:  
[iFood Restaurants Data (2020 e 2021)](https://www.kaggle.com/datasets/ricardotachinardi/ifood-restaurants-data/data)
- **2020:** ifood-restaurants-november-2020.csv  
- **2021:** ifood-restaurants-february-2021.csv  
- Bases unificadas após padronização (criação de `ano`, alinhamento de colunas).  

## Pipeline
1. Importação e inspeção inicial  
2. Criação de identificadores (`id`, `state`, `city`)  
3. Limpeza (remoção de colunas irrelevantes, tratamento de nulos)  
4. Análise exploratória (categorias, estados, preços, taxas, distâncias)  
5. Preparação de features (numéricas + categóricas OneHot)  
6. Modelagem (Linear, RandomForest, GradientBoosting, XGBoost, LightGBM)  
7. Avaliação com MAE, RMSE, R²  

## Principais Achados
- Crescimento de ~44,8k restaurantes em 2021 vs 2020.  
- Predomínio das categorias **Lanches** e **Brasileira**.  
- `delivery_fee` cresce com `distance`, mas com alta dispersão em longas distâncias.  
- `rating` extremamente concentrado (97% entre 4–5).  

## Modelagem
- MAE ~0.38 (10% da escala).  
- R² baixo (~5–7%), mesmo em modelos fortes (XGB, LGBM).  
- Interpretação: modelos acertam na média, mas não explicam variação.  

## Limitação do Target
- `rating` não é adequado como alvo → desbalanceado e influenciado por fatores não presentes na base (comida, atendimento, promoções).  
- Justifica o encerramento da modelagem preditiva neste ponto.  

## Próximos Passos
- Usar como alvo variáveis mais explicáveis (`delivery_fee`, `delivery_time`, popularidade).  
- Se insistir em `rating`: reformular como classificação binária (≥4 vs <4) com balanceamento de classes.  
- Enriquecer dados com novas variáveis externas.  

---
**Resumo:** Projeto mostra pipeline completo (EDA → ML) e destaca **limitação do target** como ponto crítico. Trabalho encerrado de forma consciente, pronto para ser evoluído caso novas variáveis sejam adicionadas.
