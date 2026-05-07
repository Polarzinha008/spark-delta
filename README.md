# Projeto Apache Spark com Delta Lake e Apache Iceberg

## 📌 Descrição

Este projeto tem como objetivo demonstrar o uso do **Apache Spark** em conjunto com as tecnologias **Delta Lake** e **Apache Iceberg**, aplicadas a um cenário de engenharia de dados.

Foram implementadas operações de manipulação de dados (DML), incluindo:

* INSERT
* UPDATE
* DELETE

Além disso, foram explorados conceitos modernos de Data Lake, como versionamento e consistência de dados.

---

## 🧠 Cenário do Projeto

O projeto simula um sistema de vendas de uma loja de eletrônicos.

A tabela utilizada possui os seguintes atributos:

* `id`: Identificador do produto
* `produto`: Nome do produto
* `preco`: Valor do produto

Esse cenário foi utilizado para demonstrar como as tecnologias Delta Lake e Apache Iceberg permitem manipular dados de forma eficiente e confiável.

---

## 🚀 Tecnologias Utilizadas

* Python 3
* Apache Spark (PySpark 3.5.1)
* Delta Lake 3.1.0
* Apache Iceberg
* Jupyter Lab
* Ubuntu (WSL)

---

## ⚙️ Configuração do Ambiente

### 1. Criar ambiente virtual do python

```bash
python3 -m venv venv
source venv/bin/activate
```

---

### 2. Instalar dependências 

```bash
pip install pyspark==3.5.1 delta-spark==3.1.0 jupyterlab
```

---

### 3. Executar o Jupyter Lab

```bash
jupyter lab
```

Abra o link gerado no navegador.

---

## 📊 Funcionalidades Implementadas

### 🔹 Delta Lake

* Criação de tabela
* Escrita e leitura de dados
* INSERT
* UPDATE
* DELETE
* Time Travel (versionamento de dados)

### 🔹 Apache Iceberg

* Criação de banco de dados
* Criação de tabela
* INSERT
* UPDATE
* DELETE

---

## 📁 Estrutura do Projeto

```
trabalho-spark/
 ├── notebooks/
 │    ├── delta-lake.ipynb
 │    └── iceberg.ipynb
 ├── README.md
 ├── .gitignore
```

---

## 🧪 Exemplos de Operações

### INSERT

```python
novo.write.format("delta").mode("append").save("/tmp/vendas")
```

---

### UPDATE

```python
deltaTable.update(
    condition="id = 2",
    set={"preco": "150"}
)
```

---

### DELETE

```python
deltaTable.delete("id = 3")
```

---

## 📚 Sobre as Tecnologias

### 🔸 Apache Spark

Framework distribuído para processamento de grandes volumes de dados, com suporte a processamento em memória e alta performance.

---

### 🔸 Delta Lake

Camada que adiciona confiabilidade ao Data Lake, permitindo:

* Transações ACID
* Versionamento de dados
* Operações UPDATE e DELETE
* Time Travel

---

### 🔸 Apache Iceberg

Formato de tabela analítico moderno que oferece:

* Evolução de schema
* Versionamento
* Melhor desempenho em consultas
* Gerenciamento eficiente de grandes volumes de dados

---

## 🎯 Conclusão

O projeto demonstrou como o uso de tecnologias modernas como Delta Lake e Apache Iceberg permite trabalhar com dados de forma estruturada, confiável e escalável.

Essas ferramentas são amplamente utilizadas em ambientes de engenharia de dados, especialmente em arquiteturas de Data Lake e Data Lakehouse.

---

## 👨‍💻 Autor(es)

* Seu Nome Aqui

---
