# Projeto Apache Spark com Delta Lake e Apache Iceberg

Trabalho da disciplina de **Arquitetura de Dados** demonstrando operações DML
(`INSERT`, `UPDATE`, `DELETE`) sobre tabelas **Delta Lake** e **Apache Iceberg**
em cima do **Apache Spark**.

A documentação conceitual completa (cenário, modelo ER, DDL e explicações) está
no MkDocs publicado:

🔗 **<https://polarzinha008.github.io/spark-delta/>**

---

## 📦 Tecnologias e versões

| Componente          | Versão  |
|---------------------|---------|
| Ubuntu (WSL)        | 22.04+  |
| Java JDK            | 17      |
| Python              | 3.10    |
| PySpark             | 3.5.1   |
| Delta Spark         | 3.1.0   |
| Apache Iceberg      | 1.4.2 (`iceberg-spark-runtime-3.5_2.12`) |
| Jupyter Lab         | última  |

---

## ⚙️ Reproduzindo o ambiente

> Estas instruções assumem **WSL com Ubuntu** no Windows. Em Linux nativo o
> procedimento é o mesmo a partir do passo 1.

### 1. Atualizar o sistema e instalar Java 17

```bash
sudo apt update
sudo apt install openjdk-17-jdk -y
```

### 2. Instalar Python 3.10

O PySpark 3.5.1 não é compatível com versões mais novas do Python, por isso fixamos o 3.10:

```bash
sudo apt install software-properties-common -y
sudo add-apt-repository ppa:deadsnakes/ppa -y
sudo apt update
sudo apt install python3.10 python3.10-venv python3.10-distutils -y
```

### 3. Garantir que o Spark use o Python 3.10

```bash
export PYSPARK_PYTHON=python3.10
export PYSPARK_DRIVER_PYTHON=python3.10
```

> Para tornar permanente, adicione essas duas linhas ao final do `~/.bashrc`.

### 4. Clonar o repositório

```bash
git clone https://github.com/Polarzinha008/spark-delta.git
cd spark-delta
```

### 5. Criar e ativar o ambiente virtual

```bash
python3.10 -m venv venv
source venv/bin/activate
```

### 6. Instalar as dependências

```bash
pip install pyspark==3.5.1 delta-spark==3.1.0 jupyterlab
```

### 7. Subir o Jupyter Lab

```bash
jupyter lab
```

Abra o link gerado no navegador e execute, na ordem, as células de:

- `notebooks/delta-lake.ipynb`
- `notebooks/iceberg.ipynb`

---

## 🧹 Resetando os dados

Os notebooks salvam os dados em `/tmp`. Para rodar do zero:

```bash
rm -rf /tmp/vendas /tmp/iceberg-warehouse /tmp/spark-warehouse
```

Em seguida, no Jupyter, vá em **Kernel → Restart Kernel** e execute as células
novamente.

---

## 📁 Estrutura

```
spark-delta/
├── notebooks/
│   ├── delta-lake.ipynb
│   └── iceberg.ipynb
├── site/                  # documentação MkDocs
│   ├── docs/
│   └── mkdocs.yml
├── README.md
└── .gitignore
```

---

## 👨‍💻 Autores

- Carine Ghisi Cadorin
- Mateus Inacio
