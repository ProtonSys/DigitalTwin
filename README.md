# Digital Twin para Esterilizador PROHS

Projeto de **Licenciatura em Engenharia Informática** dedicado ao desenvolvimento de um **Digital Twin** para um **esterilizador hospitalar a vapor saturado (PROHS)** com **pré-vácuo** e **gerador de vapor integrado**.

## Índice

- [Enquadramento](#enquadramento)
- [Problema](#problema)
- [Objetivos](#objetivos)
- [Descrição do Sistema](#descrição-do-sistema)
- [Arquitetura do Sistema](#arquitetura-do-sistema)
- [Máquina de Estados](#máquina-de-estados)
- [Utilizadores](#utilizadores)
- [Casos de Uso](#casos-de-uso)
- [Requisitos](#requisitos)
- [User Stories](#user-stories)
- [Estrutura do Repositório](#estrutura-do-repositório)
- [Tecnologias](#tecnologias)
- [Instalação](#instalação)
- [Execução](#execução)
- [Roadmap](#roadmap)
- [Bibliografia Base](#bibliografia-base)

## Enquadramento

A esterilização por vapor saturado é um processo crítico em ambiente hospitalar. Este projeto propõe a criação de um **Digital Twin** para um esterilizador PROHS, permitindo **monitorização**, **simulação**, **diagnóstico**, **validação** e **formação**.

## Problema

Os esterilizadores operam com múltiplas fases, sensores e atuadores. A análise do seu comportamento apenas no sistema físico é limitada, sobretudo para:
- diagnóstico de falhas;
- formação de utilizadores;
- validação de ciclos;
- comparação entre comportamento real e esperado.

## Objetivos

- Representar digitalmente o ciclo do esterilizador.
- Monitorizar temperatura, pressão, vácuo e estados operacionais.
- Simular o comportamento do processo.
- Detetar anomalias e gerar eventos.
- Apoiar manutenção e formação.
- Criar uma arquitetura adaptável à indústria.

## Descrição do Sistema

Sistema físico em estudo:
- Esterilizador PROHS
- Pré-vácuo
- Gerador de vapor integrado
- Sensores de temperatura, pressão, nível de água, porta e bloqueio
- Atuadores: válvulas, bomba de vácuo, aquecimento, dreno

## Arquitetura do Sistema

A arquitetura segue uma abordagem em camadas inspirada em Digital Twins industriais:

1. **Asset Layer** – esterilizador, sensores, atuadores  
2. **Connectivity Layer** – PLC, gateway, MQTT, OPC-UA, API  
3. **Digital Twin Core** – FSM, modelo do processo, motor de eventos, base de dados  
4. **Application Layer** – monitorização, diagnóstico, simulação, formação  
5. **Enterprise Layer** – relatórios, KPIs, histórico, integração futura  

## Máquina de Estados

O funcionamento do esterilizador é representado por uma **Finite State Machine (FSM)**.

### Estados principais

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
15. Falha  
16. Emergência  

## Utilizadores

- **Operador**
- **Técnico de Manutenção**
- **Engenheiro Hospitalar**
- **Formador**
- **Formando**
- **Administrador**

## Casos de Uso

- Visualizar estado do ciclo
- Ver gráficos de temperatura e pressão
- Consultar histórico de falhas
- Simular ciclos
- Comparar real vs simulado
- Criar cenários de treino
- Gerir utilizadores
- Exportar relatórios

## Requisitos

### Funcionais
- Monitorização em tempo real
- Registo de ciclos
- Simulação do processo
- Alarmística
- Comparação real vs modelo
- Gestão de utilizadores

### Não Funcionais
- Fiabilidade
- Modularidade
- Usabilidade
- Desempenho
- Escalabilidade
- Segurança

## User Stories

### US1 — Monitorização do ciclo
Como **operador**, quero **visualizar o estado do ciclo**, para **acompanhar o processo**.

### US2 — Visualização de gráficos
Como **operador**, quero **visualizar gráficos do processo**, para **analisar o comportamento do ciclo**.

### US3 — Histórico de falhas
Como **técnico de manutenção**, quero **consultar histórico de falhas**, para **identificar problemas recorrentes**.

### US4 — Análise de tendências
Como **técnico de manutenção**, quero **analisar tendências de funcionamento**, para **prever falhas**.

### US5 — Simulação do ciclo
Como **engenheiro hospitalar**, quero **simular ciclos do esterilizador**, para **validar o modelo digital**.

### US6 — Comparação real vs simulado
Como **engenheiro hospitalar**, quero **comparar o ciclo real com o simulado**, para **avaliar a precisão do Digital Twin**.

### US7 — Cenários de treino
Como **formador**, quero **criar cenários de falha**, para **treinar utilizadores**.

### US8 — Execução de treino
Como **formando**, quero **executar uma simulação guiada**, para **aprender o funcionamento do sistema**.

### US9 — Gestão de utilizadores
Como **administrador**, quero **gerir utilizadores**, para **controlar acessos**.

## Estrutura do Repositório

```text
digital-twin-sterilizer/
├── README.md
├── .gitignore
├── requirements.txt
├── main.py
├── docs/
│   ├── relatorio/
│   ├── diagramas/
│   ├── figuras/
│   └── referencias/
├── src/
│   ├── core/
│   │   ├── fsm/
│   │   ├── process_model/
│   │   ├── event_engine/
│   │   └── validation/
│   ├── data_acquisition/
│   ├── connectivity/
│   ├── simulation/
│   ├── visualization/
│   └── auth/
├── data/
│   ├── raw/
│   ├── processed/
│   ├── cycles/
│   └── logs/
├── tests/
│   ├── unit/
│   ├── integration/
│   └── validation/
├── scripts/
└── config/
    ├── app_config/
    ├── devices/
    └── simulation/
```

## Tecnologias

- Python
- MQTT
- OPC-UA
- REST API
- SQLite / PostgreSQL / InfluxDB
- Grafana / dashboards web
- PlantUML / Mermaid

## Instalação

```bash
git clone <repo-url>
cd digital-twin-sterilizer
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

## Execução

```bash
python main.py
```

## Roadmap

### Fase 1
- levantamento de requisitos
- arquitetura
- modelação FSM

### Fase 2
- aquisição e armazenamento de dados
- dashboards iniciais

### Fase 3
- simulação e validação

### Fase 4
- formação, relatórios e integração

## Bibliografia Base

- ISO 17665 — Sterilization of health care products — Moist heat
- Grieves, M. — Digital Twin: Manufacturing Excellence
- Tao, F. — Digital Twin Driven Smart Manufacturing
