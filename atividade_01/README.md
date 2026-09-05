# Atividade 01 — Perceptron e Adaline (Base Diabetes)

Implementação de um **Perceptron** e de um **Adaline** (estruturados como classes) para classificação sobre a base **diabetes** (Pima Indians Diabetes), conforme a atividade do `MiniProjeto1_v2.ipynb`.

## Objetivo

* Implementar um Perceptron como classe e treiná-lo com a base `diabetes`, avaliando a acurácia no conjunto de teste;
* Realizar experimentos com **2 taxas de aprendizado**: `0.1` e `0.01`;
* Trocar o Perceptron pelo **Adaline**, alterando a função de atualização dos pesos, e comparar convergência e resultado;
* Mostrar os resultados obtidos.

## Estrutura

```text
atividade_1_redes_neurais/
│
├── data/                          # base de dados, organizada por data
│   └── 2026-09-05/
│       └── diabetes.csv
│
└── atividade_01/
    ├── README.md
    └── codigo/
        └── MiniProjeto1_v2.ipynb
```

O notebook carrega a base diretamente de `data/2026-09-05/diabetes.csv` (caminho relativo à pasta `codigo/`, com fallback para a raiz do repositório).

## Resultados

Modelos treinados com `nIterations=100` e divisão 80/20 (`random_state=0`):

| Modelo                    | Taxa de aprendizado | Acurácia treino | Acurácia teste |
|---------------------------|---------------------|-----------------|----------------|
| Perceptron                | 0.1                 | 0.7667          | **0.7597**     |
| Perceptron                | 0.01                | 0.7667          | 0.7597         |
| Adaline                   | 0.1                 | 0.6509          | 0.6558         |
| Adaline                   | 0.01                | 0.6509          | 0.6558         |
| Adaline (taxa baixa)      | 0.001               | 0.3638          | 0.3506         |
| Adaline (taxa baixa)      | 0.0001              | 0.3491          | 0.3442         |

### Principais observações

1. **Taxas de aprendizado (0.1 e 0.01):** no Perceptron as duas taxas convergem para o mesmo modelo (~0.76 de acurácia no teste). Os erros por época oscilam sem chegar a zero, pois a base diabetes não é linearmente separável.
2. **Perceptron vs Adaline:** o Adaline não melhorou o resultado. Com `lr = 0.1` e `0.01` o custo (soma dos erros quadráticos) explodiu até overflow, pois o gradiente em lote é grande demais com as entradas normalizadas em `[0,1]`; o modelo passou a classificar quase tudo como a classe majoritária (~65% da base).
3. **Verificação extra (taxas baixas):** com `lr = 0.001` e `0.0001` o Adaline converge de forma estável, confirmando que ele é mais sensível à taxa de aprendizado que o Perceptron; porém a acurácia fica baixa (~0.35), pois a regressão linear por mínimos quadrados sobre rótulos 0/1 não separa bem este problema. O melhor resultado foi do **Perceptron (teste 0.7597)**.

## Como executar

O projeto possui scripts para **Windows (PowerShell)** e **Linux/WSL (bash)** — o `.venv` é específico da plataforma e o setup o recria automaticamente se necessário.

### Windows (PowerShell)

```powershell
.\setup.bat        # cria o .venv e instala as bibliotecas (uma única vez)
.\start.bat        # abre o Jupyter Notebook
```

### Linux / WSL (bash)

```bash
./setup.sh
./start.sh
```

Depois, abra `codigo/MiniProjeto1_v2.ipynb` e execute as células em ordem.

Dependências (instaladas via `requirements.txt`): `pandas`, `numpy`, `matplotlib`, `scikit-learn`, `jupyter`, `ipykernel`.