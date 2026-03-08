# DigitalTwin
Projeto de Licenciatura Eng. Informática

# Digital Twin industrial focado na manutenção preventiva e corretiva

Projeto de Licenciatura em Engenharia Informática.

Este projeto implementa um **Digital Twin** para um **esterilizador hospitalar a vapor saturado ** com pré-vácuo e gerador de vapor integrado.

O sistema cria uma representação digital do equipamento físico permitindo:

- monitorização do processo
- simulação do ciclo de esterilização
- diagnóstico de falhas
- análise de desempenho
- formação técnica

---

# Objetivos

Os principais objetivos do projeto são:

- representar digitalmente o ciclo de esterilização
- monitorizar parâmetros críticos do processo
- simular o comportamento do equipamento
- detetar anomalias
- apoiar manutenção preventiva
- criar um ambiente de formação técnica

---

# Arquitetura do Sistema

A arquitetura segue o modelo de **Digital Twin industrial inspirado na arquitetura Siemens / Industry 4.0**.

Camadas principais:

1. Asset Layer
2. Connectivity Layer
3. Digital Twin Core
4. Application Layer
5. Enterprise Layer

## Asset Layer

Representa o sistema físico.

Componentes:

- esterilizador PROHS
- sensores de temperatura
- sensores de pressão
- sensores de vácuo
- válvulas
- bomba de vácuo
- gerador de vapor

---

## Connectivity Layer

Responsável pela comunicação entre o equipamento e o Digital Twin.

Tecnologias possíveis:

- OPC-UA
- MQTT
- Modbus TCP
- REST API

---

## Digital Twin Core

Coração do sistema.

Componentes principais:

- máquina de estados (FSM)
- modelo matemático do processo
- motor de eventos
- base de dados de séries temporais

---

## Application Layer

Interface para os utilizadores.

Módulos principais:

- monitorização
- diagnóstico
- simulação
- formação
- gestão de alarmes

---

## Enterprise Layer

Camada de integração com sistemas externos.

Possíveis funcionalidades:

- relatórios
- análise de indicadores
- histórico de ciclos
- integração com sistemas de manutenção (CMMS)

---

# Máquina de Estados

O funcionamento do esterilizador é modelado através de uma **Finite State Machine (FSM)**.

Estados principais:

1. Standby
2. Fecho e bloqueio da porta
3. Verificações pré-ciclo
4. Gestão de água
5. Aquecimento do gerador
6. Condicionamento
7. Pré-vácuo
8. Injeção de vapor
9. Exposição
10. Descarga
11. Secagem
12. Equalização
13. Arrefecimento
14. Fim de ciclo
15. Falha / emergência

---

# Utilizadores do Sistema

## Operador
- monitorizar ciclo
- verificar resultados

## Técnico de Manutenção
- analisar falhas
- consultar histórico
- executar diagnóstico

## Engenheiro Hospitalar
- validar desempenho
- configurar parâmetros

## Formador
- criar cenários de treino

## Formando
- executar simulações

## Administrador
- gerir utilizadores

---

# User Stories

## US1 – Monitorização do ciclo

Como **operador**  
Quero **visualizar o estado do ciclo**  
Para **acompanhar o processo de esterilização**

Critérios de aceitação:

- visualizar estado atual
- visualizar temperatura
- visualizar pressão
- visualizar tempo restante

---

## US2 – Visualização de gráficos

Como **operador**  
Quero **visualizar gráficos do processo**  
Para **analisar o comportamento do ciclo**

Critérios:

- gráfico temperatura vs tempo
- gráfico pressão vs tempo
- atualização automática

---

## US3 – Histórico de falhas

Como **técnico de manutenção**  
Quero **consultar histórico de falhas**  
Para **identificar problemas recorrentes**

Critérios:

- lista de alarmes
- filtro por data
- exportação de dados

---

## US4 – Análise de tendências

Como **técnico de manutenção**  
Quero **analisar tendências de funcionamento**  
Para **prever falhas**

Critérios:

- gráficos históricos
- comparação de ciclos

---

## US5 – Simulação do ciclo

Como **engenheiro hospitalar**  
Quero **simular ciclos do esterilizador**  
Para **validar o comportamento do modelo digital**

Critérios:

- execução de simulação
- alteração de parâmetros

---

## US6 – Gestão de utilizadores

Como **administrador**  
Quero **gerir utilizadores**  
Para **controlar acessos**

Critérios:

- criar utilizador
- atribuir perfil
- remover utilizador

---

# Estrutura do Projeto
