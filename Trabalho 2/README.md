# Trabalho 2: Simulação Numérica de Pêndulos

## Descrição
Simulação e análise temporal e dinâmica dos sistemas de Equações Diferenciais Ordinárias (EDOs) que governam o comportamento cinemático de pêndulos simples e duplos. 

## Metodologia
### Pêndulo Simples
O PVI original de 2ª ordem foi modelado como sistema bidimensional acoplado. Foram aplicados e comparados três métodos independentes:
- **Euler Explícito:** Evidencia ganho dissipativo artificial por possuir limitação do erro global de $\mathcal{O}(h)$.
- **Euler Implícito:** Exige formulação de função não linear multivariada $G(U)$ com montagem de Jacobiana para cada passo. Apresenta perda numérica crônica de energia simulada.
- **Runge-Kutta 4 (RK4):** Método de ordem $\mathcal{O}(h^4)$ que se mostrou robusto à conservação da geometria energética sem distorção secular na órbita de fases.

### Pêndulo Duplo
Modelagem complexa transformando derivadas Lagrangianas em um sistema de 4 equações diferenciais restritas aos ângulos e momentos. Avaliado exclusivamente através de integração via RK4, mapeando posteriormente as coordenadas espaciais Cartesianas para plotagem das curvas dinâmicas.

## Observações Práticas
- Retratos de fase ($\dot{q} \times q$) validaram visivelmente o escoamento ou acúmulo parasita de energia nos esquemas de Euler em contraste com órbitas conservativas precisas do RK4.
- Análises no pêndulo duplo atestaram a natureza determinística, mas errática, onde ínfimas perturbações ($\Delta q \approx 0.01$) geram bifurcações imediatas na predição quando deflagradas fora do regime linear de pequenos ângulos.
