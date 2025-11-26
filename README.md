# 📊 Grafos - Estruturas de Dados & Algoritmos

> Um site educacional completo sobre **Grafos**, estruturas fundamentais da ciência da computação. Desenvolvido para a disciplina de Estruturas de Dados.

![Status](https://img.shields.io/badge/status-completo-brightgreen)
![Linguagem](https://img.shields.io/badge/linguagem-HTML%2FCSS-blue)
![Instituição](https://img.shields.io/badge/Estácio-Florianópolis-orange)

## 📝 Descrição

Este projeto é um site educacional que apresenta um **guia completo sobre grafos**, incluindo:

- ✨ Conceitos fundamentais
- 📚 Tipos de grafos (direcionados, ponderados, etc)
- 🎯 Algoritmos de busca (DFS, BFS)
- 🛤️ Algoritmos de caminhos mínimos (Dijkstra, Bellman-Ford)
- 🌐 Aplicações práticas
- 💻 Exemplos de código em Python

## 🚀 Características

### Seções Principais

1. **Conceitos Fundamentais** - Definições de vértices, arestas, graus, caminhos e ciclos
2. **Tipos de Grafos** - Classificações e características de diferentes tipos
3. **Buscas em Grafos** - DFS e BFS com implementações
4. **Algoritmos Importantes** - Componentes conexas e ordenação topológica
5. **Caminhos Mínimos** - Dijkstra e Bellman-Ford
6. **Aplicações Práticas** - Casos reais de uso em redes e otimização

### Tecnologias

- **HTML5** - Estrutura semântica
- **CSS3** - Estilização responsiva
- **Python** - Exemplos de código
- **Wikimedia Commons** - Imagens de grafos

## 📂 Estrutura do Projeto

```
Grafos/
├── index.html          # Página principal
├── styles.css          # Estilos do site
├── README.md           # Este arquivo
└── imagens/            # (Externas via Wikimedia)
```

## 💻 Exemplos de Código

### Estrutura Básica de um Grafo

```python
class Grafo:
    def __init__(self, num_vertices):
        self.num_vertices = num_vertices
        self.lista_adjacencia = [[] for _ in range(num_vertices)]
    
    def adicionar_aresta(self, u, v, peso=1):
        """Adiciona uma aresta entre u e v"""
        self.lista_adjacencia[u].append((v, peso))

    def obter_vizinhos(self, vertice):
        """Retorna os vizinhos de um vértice"""
        return self.lista_adjacencia[vertice]
```

### Busca em Profundidade (DFS)

```python
def dfs(grafo, vertice, visitado=None):
    if visitado is None:
        visitado = set()
    
    visitado.add(vertice)
    print(vertice, end=" ")
    
    for vizinho, _ in grafo.lista_adjacencia[vertice]:
        if vizinho not in visitado:
            dfs(grafo, vizinho, visitado)
```

### Busca em Largura (BFS)

```python
from collections import deque

def bfs(grafo, inicio):
    visitado = set()
    fila = deque([inicio])
    visitado.add(inicio)
    
    while fila:
        vertice = fila.popleft()
        print(vertice, end=" ")
        
        for vizinho, _ in grafo.lista_adjacencia[vertice]:
            if vizinho not in visitado:
                visitado.add(vizinho)
                fila.append(vizinho)
```

### Algoritmo de Dijkstra

```python
import heapq

def dijkstra(grafo, origem):
    distancias = {i: float('inf') for i in range(grafo.num_vertices)}
    distancias[origem] = 0
    pq = [(0, origem)]
    visitado = set()
    
    while pq:
        dist_atual, u = heapq.heappop(pq)
        if u in visitado:
            continue
        visitado.add(u)
        
        for v, peso in grafo.lista_adjacencia[u]:
            if v not in visitado:
                nova_dist = dist_atual + peso
                if nova_dist < distancias[v]:
                    distancias[v] = nova_dist
                    heapq.heappush(pq, (nova_dist, v))
    
    return distancias
```

## 🎯 Complexidade de Algoritmos

| Algoritmo | Complexidade | Tipo |
|-----------|-------------|------|
| DFS | O(V + E) | Busca |
| BFS | O(V + E) | Busca |
| Dijkstra | O((V + E) log V) | Caminhos Mínimos |
| Bellman-Ford | O(V × E) | Caminhos Mínimos |
| Ordenação Topológica | O(V + E) | Ordenação |

## 🌐 Aplicações Práticas

- **Redes Sociais** - Análise de conexões entre usuários
- **Roteamento** - GPS, internet, logística
- **Redes de Computadores** - Topologia e protocolos
- **Biologia** - Análise de redes proteicas
- **Compiladores** - Análise de dependências
- **Otimização** - Problema do Caixeiro Viajante (TSP)

## 📖 Como Usar

1. Abra `index.html` em seu navegador
2. Navegue pelas diferentes seções usando o menu
3. Leia os conceitos explicados
4. Estude os exemplos de código em Python
5. Veja as imagens e diagramas dos grafos

## 👤 Autor

**Luana Santini**
- 🎓 Sistemas de Informação
- 🏫 Estácio Florianópolis
- 📚 Matrícula: 202308416251

## 📄 Licença

Este projeto é fornecido para fins educacionais.

## 🔗 Links Úteis

- [Wikimedia Commons - Grafos](https://commons.wikimedia.org/)
- [Documentação Python](https://docs.python.org/)
- [Wikipedia - Grafo](https://pt.wikipedia.org/wiki/Grafo)

## 📝 Notas

- Todos os exemplos de código são em **Python**
- As imagens são obtidas da **Wikimedia Commons**
- O site é **responsivo** e funciona em navegadores modernos
- Desenvolvido para fins **educacionais**

---

**Última atualização:** Novembro 2025

