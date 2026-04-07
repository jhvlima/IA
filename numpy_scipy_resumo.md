# NumPy e SciPy para Inteligência Artificial

## 📚 Sumário

1. [NumPy](#numpy)
2. [SciPy](#scipy)
3. [Aplicações em IA](#aplicações-em-ia)
4. [Comparação](#comparação)

---

## NumPy

### O que é?

NumPy (Numerical Python) é a biblioteca fundamental para computação numérica em Python. Fornece suporte para arrays multidimensionais e ferramentas para trabalhar com esses arrays.

### Características Principais

#### 1. **Arrays N-dimensionais (ndarray)**

```python
import numpy as np

# Criando arrays
arr1d = np.array([1, 2, 3, 4, 5])          # 1D
arr2d = np.array([[1, 2, 3], [4, 5, 6]])   # 2D

# Arrays especiais
zeros = np.zeros((3, 3))       # Matriz de zeros
ones = np.ones((2, 4))         # Matriz de uns
eye = np.eye(3)                # Matriz identidade
rand = np.random.rand(3, 3)    # Números aleatórios
```

#### 2. **Operações Vetorizadas**

- Muito mais rápidas que loops Python puro
- Operações elemento a elemento

```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

# Operações diretas (vetorizadas)
c = a + b           # [5, 7, 9]
d = a * b           # [4, 10, 18]
e = np.sqrt(a)      # Raiz quadrada
```

#### 3. **Álgebra Linear**

```python
# Produto de matrizes
A = np.array([[1, 2], [3, 4]])
B = np.array([[5, 6], [7, 8]])
C = np.dot(A, B)    # ou A @ B

# Determinante
det = np.linalg.det(A)

# Autovalores e autovetores
eigenvalues, eigenvectors = np.linalg.eig(A)

# Inversa
A_inv = np.linalg.inv(A)
```

#### 4. **Funções Matemáticas**

```python
# Trigonométricas
sin_vals = np.sin(np.array([0, np.pi/2, np.pi]))

# Exponenciais e logaritmos
exp_vals = np.exp(np.array([1, 2, 3]))
log_vals = np.log(np.array([1, 2.718, 7.389]))

# Estatísticas
mean = np.mean(arr)
std = np.std(arr)
max_val = np.max(arr)
min_val = np.min(arr)
```

#### 5. **Manipulação de Dados**

```python
# Reshape
reshaped = arr.reshape(3, 3)

# Transposição
transposed = arr.T

# Flatten
flattened = arr.flatten()

# Concatenação
combined = np.concatenate([arr1, arr2])

# Indexação avançada
filtered = arr[arr > 5]  # Elementos maiores que 5
```

### Por que NumPy é importante para IA?

- **Base de dados**: Representação eficiente de datasets
- **Velocidade**: Operações ~100x mais rápidas que Python puro
- **Compatibilidade**: Padrão para todas as bibliotecas ML (TensorFlow, PyTorch, scikit-learn)
- **Memória**: Uso otimizado de memória para grandes volumes

---

## SciPy

### O que é?

SciPy (Scientific Python) é construída sobre NumPy e fornece algoritmos e funções para computação científica avançada.

### Características Principais

#### 1. **Submodelos Principais**

| Módulo | Função |
|--------|--------|
| `scipy.stats` | Distribuições e testes estatísticos |
| `scipy.optimize` | Otimização e encontro de raízes |
| `scipy.linalg` | Álgebra linear avançada |
| `scipy.interpolate` | Interpolação de dados |
| `scipy.signal` | Processamento de sinais |
| `scipy.spatial` | Estruturas e distâncias espaciais |
| `scipy.integrate` | Integração numérica |
| `scipy.fft` | Transformada rápida de Fourier |

#### 2. **Estatísticas (scipy.stats)**

```python
from scipy import stats

# Distribuições
dist = stats.norm(loc=0, scale=1)  # Distribuição normal
pdf = dist.pdf(0)                   # Função densidade probabilidade
cdf = dist.cdf(1)                   # Função distribuição cumulativa
sample = dist.rvs(size=1000)        # Amostragem

# Testes estatísticos
data1 = [1, 2, 3, 4, 5]
data2 = [2, 3, 4, 5, 6]
t_stat, p_value = stats.ttest_ind(data1, data2)  # Teste t

# Correlação
corr, p_val = stats.pearsonr(data1, data2)
```

#### 3. **Otimização (scipy.optimize)**

```python
from scipy.optimize import minimize, minimize_scalar

# Minimizar função
def func(x):
    return (x - 3)**2 + 2

result = minimize(func, x0=0)  # Minimização
print(result.x)  # Valor ótimo

# Encontrar raiz
def equation(x):
    return x**2 - 4

from scipy.optimize import fsolve
root = fsolve(equation, x0=0)  # root ≈ 2
```

#### 4. **Álgebra Linear Avançada (scipy.linalg)**

```python
from scipy.linalg import eig, svd, cholesky

# SVD - Decomposição em Valores Singulares
U, s, Vt = svd(matrix)

# Autovalores/Autovetores
eigenvalues, eigenvectors = eig(matrix)

# Decomposição de Cholesky
L = cholesky(matrix)
```

#### 5. **Distâncias Espaciais (scipy.spatial)**

```python
from scipy.spatial.distance import euclidean, cosine

# Distâncias
p1 = [0, 0]
p2 = [3, 4]
dist_euclidean = euclidean(p1, p2)  # 5.0
dist_cosine = cosine([1, 0, 1], [1, 1, 0])  # Similaridade

# K-d tree para busca rápida
from scipy.spatial import cKDTree
tree = cKDTree([p1, p2])
query = tree.query([1, 1])
```

#### 6. **Processamento de Sinais (scipy.signal)**

```python
from scipy import signal

# Aplicar filtro
filtered = signal.convolve([1, 2, 3], [0.5, 0.5])

# Detecção de picos
peaks, _ = signal.find_peaks(data)
```

---

## Aplicações em IA

### NumPy + SciPy na Prática

#### 1. **Pré-processamento de Dados**

```python
import numpy as np
from scipy import stats

# Normalização (Z-score)
data_normalized = stats.zscore(raw_data)

# Padronização
mean = np.mean(raw_data, axis=0)
std = np.std(raw_data, axis=0)
data_standardized = (raw_data - mean) / std
```

#### 2. **Operações em Datasets**

```python
# Dividir treino/teste
indices = np.random.permutation(len(data))
train_size = int(0.8 * len(data))
train_indices = indices[:train_size]
test_indices = indices[train_size:]

X_train = X[train_indices]
X_test = X[test_indices]
```

#### 3. **Cálculo de Distâncias (Recomendação)**

```python
from scipy.spatial.distance import cdist

# Matriz de distâncias entre usuários
distances = cdist(user_features, user_features, metric='euclidean')
```

#### 4. **Otimização de Modelo**

```python
from scipy.optimize import minimize

def loss_function(weights):
    predictions = np.dot(X, weights)
    return np.mean((predictions - y)**2)

result = minimize(loss_function, x0=initial_weights)
optimal_weights = result.x
```

#### 5. **Análise de Componentes Principais (PCA)**

```python
# Redução de dimensionalidade com SVD
from scipy.linalg import svd

U, s, Vt = svd(X, full_matrices=False)
# s contém a importância de cada componente
explained_variance = (s**2) / np.sum(s**2)
```

---

## Comparação

### NumPy vs SciPy vs Alternativas

| Aspecto | NumPy | SciPy | Pandas | TensorFlow |
|--------|-------|-------|--------|-----------|
| **Uso Principal** | Arrays e álgebra linear | Algoritmos científicos | DataFrames e análise | Deep Learning |
| **Performance** | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ (GPU) |
| **Dimensões** | Até ~8-10 | Vetorial | Tabular | Arbitrária |
| **GPU Support** | Não | Não | Não | Sim |
| **Algoritmos ML** | Básicos | Intermediários | Análise exploratória | Avançados (DL) |

### Stack Típico em IA

```
Deep Learning/Neural Networks
         ↓
    TensorFlow/PyTorch
         ↓
    Scikit-learn (ML clássico)
         ↓
    SciPy (Operações científicas)
         ↓
    NumPy (Arrays e álgebra)
         ↓
    Python (Base)
```

---

## Instalação Rápida

```bash
# Instalar NumPy e SciPy
pip install numpy scipy

# Com Conda (recomendado)
conda install numpy scipy

# Verificar instalação
python -c "import numpy as np; import scipy; print(np.__version__, scipy.__version__)"
```

---

## Referências Rápidas

### Documentação Oficial

- NumPy: <https://numpy.org/doc/>
- SciPy: <https://docs.scipy.org/>

### Cheat Sheets Úteis

- NumPy: <https://datacamp.com/cheat-sheet/numpy-cheat-sheet-data-analysis-in-python>
- SciPy: <https://datacamp.com/cheat-sheet/scipy-cheat-sheet-linear-algebra-in-python>

---

## Resumo Final

| Biblioteca | Para Quê? | Quando Usar |
|-----------|-----------|-------------|
| **NumPy** | Computação numérica e álgebra linear | Sempre que trabalhar com arrays/matrizes |
| **SciPy** | Algoritmos cientificamente otimizados | Otimização, estatísticas, FFT, integração |

**Dica:** Em IA moderna, você frequentemente usará NumPy/SciPy como base, evoluindo para TensorFlow/PyTorch conforme a complexidade aumenta.
