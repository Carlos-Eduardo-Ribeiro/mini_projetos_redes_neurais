# Mini Projetos — Redes Neurais

Repositório acadêmico destinado ao armazenamento e organização de **códigos, exercícios, atividades e mini projetos desenvolvidos na disciplina de Redes Neurais** durante a graduação em Ciência da Computação.

O repositório funciona como um espaço para registrar a evolução prática dos estudos relacionados a **Redes Neurais Artificiais, Machine Learning e Inteligência Artificial**.

## 🎯 Objetivo

Centralizar os materiais práticos desenvolvidos ao longo da disciplina, mantendo os códigos organizados e documentados para facilitar:

* 📚 Estudos e revisões;
* 💻 Prática de programação;
* 🧠 Experimentação com Redes Neurais;
* 📊 Análise dos resultados dos modelos;
* 📝 Registro das atividades acadêmicas;
* 🔎 Consulta e reutilização dos projetos desenvolvidos.

## 📂 Organização

Os projetos e atividades são organizados de acordo com os conteúdos trabalhados durante a disciplina.

Uma estrutura possível para o repositório é:

```text
atividade_1_redes_neurais/
│
├── data/                     # bases de dados, organizadas por data
│   └── 2026-09-05/
│       └── diabetes.csv
│
├── atividade_01/
│   ├── README.md
│   └── codigo/
│       └── MiniProjeto1_v2.ipynb
│
├── atividade_02/
│   ├── README.md
│   └── codigo/
│
├── mini_projeto_01/
│   ├── README.md
│   ├── notebooks/
│   └── src/
│
├── .venv/                    # ambiente virtual (ignorado pelo git)
├── requirements.txt
├── setup.sh
├── start.sh
├── setup.bat
├── start.bat
├── .gitignore
└── README.md
```

A estrutura pode ser modificada conforme novos conteúdos e atividades forem adicionados.

## 🧠 Conteúdos

Entre os principais conceitos que podem ser explorados nos projetos estão:

* Redes Neurais Artificiais;
* Perceptron;
* Multi-Layer Perceptron (MLP);
* Funções de ativação;
* Forward Propagation;
* Backpropagation;
* Funções de perda;
* Otimizadores;
* Treinamento de modelos;
* Validação e avaliação;
* Classificação;
* Regressão;
* Overfitting e Underfitting;
* Métricas de avaliação;
* Experimentação com diferentes arquiteturas.

## 🛠️ Tecnologias

As tecnologias e bibliotecas utilizadas podem variar de acordo com cada atividade. Entre elas:

* **Python**
* **NumPy**
* **Pandas**
* **Matplotlib**
* **Scikit-learn**
* **PyTorch**
* **Jupyter Notebook**

## 🚀 Como executar

As atividades utilizam um ambiente virtual Python (`.venv/`) para isolar as dependências. Existem scripts para **Windows (PowerShell)** e para **Linux/WSL (bash)**. O `.venv` é específico da plataforma; o script de setup recria automaticamente o ambiente caso ele tenha sido criado em outra plataforma.

### Windows (PowerShell)

```powershell
.\setup.bat        # cria o .venv e instala as bibliotecas (uma única vez)
.\start.bat        # abre o Jupyter Notebook com o .venv
```

### Linux / WSL (bash)

```bash
./setup.sh
./start.sh
```

Ambos os `setup.*` criam a pasta `.venv/`, garantem o `pip`, instalam as bibliotecas listadas em `requirements.txt` e registram o kernel do Jupyter.

### Executando manualmente

```bash
python -m venv .venv
.venv\Scripts\activate        # Windows
source .venv/bin/activate     # Linux/WSL
pip install -r requirements.txt
jupyter notebook
```

### 3. Executar a atividade

Abra o notebook da atividade desejada (ex.: `atividade_01/codigo/MiniProjeto1_v2.ipynb`) e execute as células em ordem. As atividades carregam as bases de dados a partir de `data/<data>/`.

### `requirements.txt`

Contém as bibliotecas utilizadas no projeto (`pandas`, `numpy`, `matplotlib`, `scikit-learn`, `jupyter`, `ipykernel`, entre outras). Para instalá-las em um ambiente existente:

```bash
pip install -r requirements.txt
```

> **Observação:** a pasta `.venv/` é ignorada pelo `.gitignore`. Os arquivos `.csv` **não** são ignorados e são versionados normalmente.

## 📌 Sobre

Este repositório possui finalidade **acadêmica e educacional**, reunindo as práticas realizadas durante a disciplina de Redes Neurais.

Os códigos representam o processo de aprendizado e experimentação com diferentes conceitos, técnicas e modelos de Redes Neurais.

---

**Autor:** Carlos Eduardo Ribeiro
**Curso:** Ciência da Computação
**Instituição:** Universidade Federal Rural de Pernambuco (UFRPE)
