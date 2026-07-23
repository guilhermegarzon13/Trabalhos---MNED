# Trabalho 3: Estudo Numérico da Equação de Advecção-Difusão

## Descrição
Avaliação técnica do comportamento e sensibilidade do processo de transporte, onde variáveis se propagam simultaneamente por fluxos advectivos direcionados e dissipam por potenciais difusivos, dependendo explicitamente da razão fundamental definida pelo Número de Péclet ($Pe$).

## Abordagens Numéricas (MOL)
O problema transiente foi avaliado via discretização no tempo utilizando esquema de progresso frontal (Euler Explícito). Diferentes estratégias espaciais foram avaliadas:
1. **Diferenças Centrais (FTCS):** Apropriado apenas para domínio com predominância difusiva.
2. **Método Upwind:** Modela a variação espacial considerando exclusivamente referencial a montante em relação à orientação convectiva, introduzindo intencionalmente uma ordem residual atuando como difusão artificial.

## Análise e Conclusões Principais
- **Análise de Estabilidade (Von Neumann):** Obteve-se de maneira sistemática os fatores de amplificação algorítmica para os dois métodos. Confirmou-se analiticamente que a presença de diferenças centradas cria uma sub-restrição de estabilidade grave ($\Delta t \le 2/Pe$) que frequentemente colapsa os cálculos caso $Pe \gg 1$.
- **Conflito de Domínios Físicos:** Para o regime puramente advectivo ($Pe = 300$), o FTCS produziu oscilações espúrias descontroladas com coeficientes invertidos, resultando em matrizes com diagonais adjacentes que provocam anomalias na positividade do calor, distorcendo o sentido de transporte. O Upwind demonstrou comportamento monotônico, com obediência formal à condição Courant–Friedrichs–Lewy (CFL).
- O número $Pe$ mostrou-se a métrica obrigatória para determinar o tradeoff numérico: viabilidade de malha e passo temporal explícito ditam que esquemas simples de Euler são úteis primariamente para transporte dominado por advecção (CFL governante); caso a modelagem seja fortemente dominada por decaimento difusivo, os custos computacionais da restrição $\mathcal{O}(\Delta x^2)$ tornam os esquemas implícitos estritamente preferíveis no uso real.
