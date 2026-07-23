# Métodos Numéricos em Equações Diferenciais (SME0202)

Este repositório contém três trabalhos focados na modelagem, resolução e análise de equações diferenciais por meio de métodos numéricos. Desenvolvido por Guilherme da Mata Garzon (15456601).

## Estrutura do Repositório

- **Trabalho 1: Análise Numérica de Equações Elípticas**
  Resolução de um problema estacionário de convecção-difusão bidimensional via diferenças finitas de segunda ordem. Contém análise empírica e analítica de erros e convergência.
- **Trabalho 2: Simulação Numérica de Pêndulos**
  Integração numérica de sistemas de EDOs não-lineares para a modelagem de pêndulos simples e duplos. Foco na propagação de erros, conservação de energia geométrica e sensibilidade a condições iniciais.
- **Trabalho 3: Equação Advecção-Difusão**
  Estudo numérico transitório de fluxos de advecção-difusão. Avalia limitações e aplicabilidade de esquemas com base no Número de Péclet ($Pe$) e estabilidade de Von Neumann.

## Requisitos Técnicos
As implementações e análises numéricas requerem o uso de Python 3, além das bibliotecas:
- `numpy`: Estruturação e manipulação de vetores.
- `scipy` (`scipy.sparse` e `scipy.optimize`): Otimização de alocação de matrizes esparsas, resolução de sistemas lineares grandes e sistemas não lineares (Método de Newton).
- `matplotlib`: Renderização de superfícies 3D, mapas de erro espacial e diagramas log-log de convergência.
