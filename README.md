# Lista 2 – Condução e Solução de Blasius em Python

**Disciplina:** Tópicos Especiais de Energia – Transferência de Calor utilizando PINNs (UFABC, 3º quadrimestre de 2026)
**Professores:** Prof. Dr. Daniel Jonas Dezan e Prof. MSc. Paulo de Souza Silva
**Aluno:** _preencher com o nome completo_

Resolução dos cinco exercícios da Lista 2, um notebook por exercício, baseada nos notebooks de apoio do repositório da disciplina ([HeatTransferPINN](https://github.com/Paulo-de-Souza/HeatTransferPINN)). Todos os notebooks estão salvos **já executados**, com saídas e gráficos.

| Exercício | Tema | Notebook | Colab |
|---|---|---|---|
| 1 | Condução 1D sem geração (solução analítica) | [Exercicio1.ipynb](Exercicio1.ipynb) | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/engnivaldop/lista2-transcal-pinns/blob/main/Exercicio1.ipynb) |
| 2 | Condução 1D com geração + diferenças finitas | [Exercicio2.ipynb](Exercicio2.ipynb) | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/engnivaldop/lista2-transcal-pinns/blob/main/Exercicio2.ipynb) |
| 3 | Placa 2D: série analítica × diferenças finitas | [Exercicio3.ipynb](Exercicio3.ipynb) | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/engnivaldop/lista2-transcal-pinns/blob/main/Exercicio3.ipynb) |
| 4 | Capacitância global e número de Biot | [Exercicio4.ipynb](Exercicio4.ipynb) | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/engnivaldop/lista2-transcal-pinns/blob/main/Exercicio4.ipynb) |
| 5 | Camadas-limite de Blasius (hidrodinâmica e térmica) | [Exercicio5.ipynb](Exercicio5.ipynb) | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/engnivaldop/lista2-transcal-pinns/blob/main/Exercicio5.ipynb) |

## Principais resultados

- **Ex. 1:** perfis lineares com gradientes de −50 K/m (300→200 K) e −150 K/m (500→200 K).
- **Ex. 2:** $T_{max}$ = 812,5 K em x = 0. Diferenças finitas com 5 e 11 pontos coincidem com a analítica nos nós (erro ~10⁻¹³ K), pois a solução é parabólica.
- **Ex. 3:** temperatura no centro = 494,18 K (N = 1), 483,73 K (N = 5), 483,54 K (N = 10), 483,53 K (N = 100). Diferenças finitas: 478,78 K (5×5) e 482,66 K (11×11). Na malha 11×11, erro máximo de 300 K nos cantos superiores (descontinuidade da condição de contorno) e erro médio de 5,8 K. Nos nós internos: máximo 7,5 K, médio 0,9 K.
- **Ex. 4:** Bi = 0,067 (aço, capacitância global adequada, erro máx. 0,008·θ₀) e Bi = 10 (isolante, inadequada, erro máx. 0,45·θ₀).
- **Ex. 5:** f''(0) = 0,33206 e η₉₉ = 4,91. δ₉₉ = 2,69 / 4,66 / 5,70 mm em x = 0,2 / 0,6 / 0,9 m. θ'(0) = −0,2149 (Pr = 0,3), −0,4223 (Pr = 2), −0,5767 (Pr = 5). Resultados conferidos com o HTML interativo da disciplina.

## Como executar

No Google Colab, basta clicar nos botões acima. Localmente:

```bash
python3 -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook
```

O Exercício 4 leva cerca de 2 minutos para rodar, porque a solução explícita do caso do aço usa cerca de 2,8 milhões de passos de tempo. As figuras são salvas em [`figuras/`](figuras) com 300 dpi.

> Desenvolvido com auxílio de ferramentas de IA, como permitido no enunciado da lista. O código foi executado e os resultados conferidos.
