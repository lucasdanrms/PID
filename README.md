# Robô Seguidor de Linha com Controlador PID no CoppeliaSim 

Este repositório contém o projeto de simulação de um robô seguidor de linha desenvolvido no ambiente **CoppeliaSim**. O controle de navegação do robô é realizado através de um **Controlador PID (Proporcional, Integral e Derivativo)** escrito em **Lua**, garantindo que o robô faça curvas suaves e mantenha a estabilidade na pista.

## 🛠️ Tecnologias e Ferramentas Utilizadas
* **Simulador:** CoppeliaSim (V-REP)
* **Linguagem:** Lua (via *Child Scripts* nativos do simulador)
* **Controle:** Algoritmo PID Clássico
* **Cinemática:** Acionamento Diferencial (Differential Drive)
* **Percepção:** Sensores de Visão Ortográficos (Filtro de intensidade de cor)

## 🧠 Arquitetura do Sistema

O sistema foi modelado para traduzir o mundo físico da simulação em variáveis matemáticas que o algoritmo de controle possa processar:

1. **Input (Sensores):** O robô possui 3 sensores de visão apontados para o chão, configurados para detectar a alta intensidade da linha branca sobre o piso escuro.
2. **Processamento (Cálculo do Erro):** O script avalia qual sensor detectou a linha e atribui um valor de "Erro" posicional (-1 para a direita, +1 para a esquerda, 0 para centralizado).
3. **Controle (PID):** O algoritmo calcula a ação corretiva com base no Erro atual (Proporcional) e na taxa de variação do erro (Derivativo). *Nota: O ganho Integral (Ki) foi mantido em 0 devido à ausência de erros de regime permanente neste ambiente de simulação específico.*
4. **Output (Atuação):** O sinal de controle gerado ajusta dinamicamente a velocidade individual da roda esquerda e direita, forçando o robô a pivotar e corrigir sua trajetória.

## 🚀 Como Executar o Projeto

Para testar esta simulação na sua máquina, siga os passos abaixo:

1. **Instale o CoppeliaSim:** Certifique-se de ter o [CoppeliaSim](https://www.coppeliarobotics.com/) instalado (versão Edu/Player).
2. **Clone o repositório:**
   ```bash
   git clone (https://github.com/lucasdanrms/PID)
