Este repositório reúne **anotações, códigos e aprendizados** desenvolvidos durante uma imersão prática em **Análise de Dados com Python**. O foco do projeto é documentar, de forma didática, cada conceito abordado ao longo da jornada, com explicações claras sobre o uso de **bibliotecas, métodos e funções específicas do ecossistema Python** aplicadas à análise de dados.

<img width="1866" height="912" alt="Opera Instantâneo_2026-02-03_031201_imersaoalurapython-erickida streamlit app" src="https://github.com/user-attachments/assets/44f86a73-5f9b-4848-ac8a-9972d03aab53" />

## 🎯 Objetivo do Repositório

* Documentar o conteúdo aprendido durante uma imersão em Análise de Dados
* Explicar cada trecho de código de forma clara e didática
* Servir como material de estudo e consulta
* Demonstrar a aplicação prática de bibliotecas de Python para dados

---

## 🧰 Tecnologias e Bibliotecas Utilizadas

Abaixo estão listadas **todas as bibliotecas utilizadas ao longo do projeto**, com uma breve descrição do papel de cada uma no processo de análise de dados.

### Python

Linguagem base do projeto, responsável por toda a lógica, manipulação e análise dos dados.

---

### Pandas (`pd`)

Biblioteca central para **manipulação e análise de dados estruturados**.

Utilizada para:

* Leitura de arquivos CSV (`read_csv`)
* Criação e manipulação de DataFrames
* Limpeza e transformação de dados
* Agrupamentos (`groupby`)
* Cálculo de métricas estatísticas (`mean`, `describe`)

Exemplo de uso:

```python
    df['ano'].unique()
```

---

### NumPy (`np`)

Biblioteca de **computação numérica** utilizada como base para operações matemáticas e suporte a estruturas de dados numéricos.

Utilizada principalmente para:

* Operações numéricas
* Suporte a cálculos estatísticos
* Integração com Pandas e outras bibliotecas

Exemplo de uso:

```python
df_temperaturas = pd.DataFrame({
    'dia': ['segunda', 'terca', 'quarta', 'quinta', 'sexta'],
    'temperatura': [30, np.nan, np.nan, 28, 27]
})
```

---

### Seaborn (`sns`)

Biblioteca de visualização construída sobre o Matplotlib, focada em **gráficos estatísticos mais elaborados**.

Utilizada para:

* Visualizações estatísticas
* Gráficos com melhor estética padrão
* Exploração visual de padrões nos dados

Exemplo de uso:

```python
ordemSenioridade = ['Junior', 'Pleno', 'Senior', 'Executivo']

plt.figure(figsize=(8, 5))
sns.boxplot(x='senioridade', y='usd', data=df_limpo, order=ordemSenioridade)
plt.title('Distribuicao salarial por nivel de senioridade')
plt.xlabel('Senioridade')
plt.ylabel('USD')
plt.show()
```

---

### Matplotlib (`plt`)

Biblioteca de **visualização de dados** tradicional do ecossistema Python.

Utilizada para:

* Criação de gráficos estáticos
* Personalização básica de visualizações
* Apoio à análise exploratória

Exemplo de uso:

```python
plt.figure(figsize=(8, 5))
sns.barplot(data=df_limpo, x='senioridade', y='usd')
plt.title('Salario medio por nivel de senioridade')
plt.xlabel('Senioridade')
plt.ylabel('Salario Anual (USD)')

plt.show()
```
---

### plotly.express (`px`)

Biblioteca para **visualização de dados interativa**.

Utilizada para:

* Criação de gráficos interativos
* Gráficos de barras comparativos
* Melhor visualização de métricas e categorias

Exemplo de uso:

```python
senioridade_media_salario = df_limpo.groupby('senioridade')['usd'].mean().sort_values(ascending=False).reset_index()
fig = px.bar(
    senioridade_media_salario,
    x='senioridade',
    y='usd',
    title='Média Salarial por Senioridade',
    labels={'senioridade': 'Nível de Senioridade', 'usd': 'Média Salarial Anual (USD)'}
)

fig.show()
```

---

### PyCountry (`pycountry`)

Biblioteca utilizada para **padronização e manipulação de informações relacionadas a países**.

Utilizada para:

* Conversão e validação de nomes e códigos de países
* Apoio à organização de dados geográficos

Exemplo de uso:

```python
def iso2_to_iso3(code):
    try:
        return pycountry.countries.get(alpha_2=code).alpha_3
    except:
        return None
```
---

### Manipulação de Dados

Nesta etapa foi apresentado como trabalhar com dados reais:

* Importação de bases de dados
* Entendimento da estrutura das tabelas
* Seleção de colunas específicas
* Criação de variáveis a partir de operações com dados

Exemplo conceitual:

* Agrupar dados por uma categoria (ex: senioridade)
* Calcular métricas como média salarial
* Reorganizar os dados para visualização

---

### Análise Exploratória de Dados (EDA)

* Identificação de padrões
* Comparação entre grupos
* Interpretação de métricas
* Transformação de dados brutos em insights

---

### Visualização de Dados

* Criação de gráficos para facilitar a interpretação
* Uso de gráficos de barras para comparação
* Importância de títulos e labels claros
* Visualização como ferramenta de tomada de decisão

---

## 📁 Estrutura do Projeto

```
📦 imersao-analise-dados-python
 ┣ 📜 README.md
 ┣ 📜 app.py
 ┣ 📜 dadosImersaoAlura.csv
 ┣ 📜 AulasPython_ImersaoAlura.ipynb
 ┣ 📜 requirements.txt

```

* `README.md`: Documentação do projeto e explicação dos aprendizados
* `app.py`: Visualização web do projeto da Análise de Dados
* `dadosImersaoAlura.csv`: Todo o DataFrame modificado durante as aulas
* `AulasPython_ImersaoAlura.ipynb`: Notebook com todas as aulas, anotações e códigos
* `requirements.txt`: Bibliotecas obrigatórias para o funcionamento do código

---

## 🚀 Considerações Finais

Este repositório foi desenvolvido com foco em **aprendizado prático e documentação clara**, priorizando a compreensão do funcionamento das bibliotecas e ferramentas utilizadas em Análise de Dados com Python.

O conteúdo aqui apresentado serve como base de estudo, revisão e referência para projetos futuros na área de dados.

---

📌 *Projeto desenvolvido durante a Imersão da Alura em Análise de Dados com Python.*
