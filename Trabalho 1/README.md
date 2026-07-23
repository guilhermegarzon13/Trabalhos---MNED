# Trabalho 1: Análise Numérica de Equações Elípticas

## Descrição
Este trabalho realiza a resolução numérica de um problema de fronteira bidimensional governado por uma equação diferencial parcial elíptica com termos de convecção e difusão. O modelo simula a distribuição estacionária de temperatura em uma placa retangular com geração térmica interna nula e vetor velocidade direcionado ao eixo y.

## Metodologia
- **Discretização Numérica:** Utilização de diferenças finitas de ordem de convergência $\mathcal{O}(h^2)$ para as derivadas (operador de diferenças centrais).
- **Tratamento de Contorno:** Mapeamento de condições de Dirichlet explícitas e condições de Neumann e Robin via criação de nós fantasmas artificiais nas fronteiras e vértices do domínio.
- **Resolução Linear:** Transformação bidimensional dos nós em arranjos unidimensionais $(k = j \cdot m + i - 1)$ para formação da matriz global esparsa pentadiagonal resolvida eficientemente pelas rotinas do `scipy.sparse`.

## Resultados e Verificações
1. **Erro de Truncamento Local (ETL):** O desenvolvimento teórico da série de Taylor determinou a expressão analítica rigorosa para a flutuação do erro, confirmando que as variações estão atreladas a fatores periódicos transversais e caimentos exponenciais logitudinais do domínio físico.
2. **Convergência:** Foram simuladas progressões de diminuição de malha, comprovando em escala logarítmica que a aproximação converge estritamente a $p pprox 1.99$, em concordância rigorosa com a referência teórica quadrática esperada.
