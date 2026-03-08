# Digital Twin para Esterilizador PROHS

Projeto de **Licenciatura em Engenharia Informática** dedicado ao desenvolvimento de um **Digital Twin** para um **esterilizador hospitalar a vapor saturado (PROHS)** com **pré-vácuo** e **gerador de vapor integrado**.

## Índice

- [1. Enquadramento](#1-enquadramento)
- [2. Problema](#2-problema)
- [3. Objetivos](#3-objetivos)
- [4. Objetivos Específicos](#4-objetivos-específicos)
- [5. Questão de Investigação / Motivação](#5-questão-de-investigação--motivação)
- [6. Descrição do Sistema](#6-descrição-do-sistema)
- [7. O que é um Digital Twin neste projeto](#7-o-que-é-um-digital-twin-neste-projeto)
- [8. Arquitetura do Sistema](#8-arquitetura-do-sistema)
- [9. Arquitetura Digital Twin estilo Siemens / Industry 4.0](#9-arquitetura-digital-twin-estilo-siemens--industry-40)
- [10. Máquina de Estados do Esterilizador](#10-máquina-de-estados-do-esterilizador)
- [11. Utilizadores do Sistema](#11-utilizadores-do-sistema)
- [12. Casos de Uso Principais](#12-casos-de-uso-principais)
- [13. Requisitos Funcionais](#13-requisitos-funcionais)
- [14. Requisitos Não Funcionais](#14-requisitos-não-funcionais)
- [15. User Stories](#15-user-stories)
- [16. Product Backlog Resumido](#16-product-backlog-resumido)
- [17. Estrutura do Repositório](#17-estrutura-do-repositório)
- [18. Tecnologias e Ferramentas](#18-tecnologias-e-ferramentas)
- [19. Modelo de Dados Esperado](#19-modelo-de-dados-esperado)
- [20. Fluxo de Funcionamento](#20-fluxo-de-funcionamento)
- [21. Simulação e Validação](#21-simulação-e-validação)
- [22. Instalação](#22-instalação)
- [23. Execução](#23-execução)
- [24. Resultados Esperados](#24-resultados-esperados)
- [25. Aplicabilidade Industrial](#25-aplicabilidade-industrial)
- [26. Roadmap](#26-roadmap)
- [27. Estado Atual do Projeto](#27-estado-atual-do-projeto)
- [28. Riscos e Limitações](#28-riscos-e-limitações)
- [29. Bibliografia Base](#29-bibliografia-base)
- [30. Autor](#30-autor)

---

## 1. Enquadramento

A esterilização por vapor saturado é um processo crítico em ambiente hospitalar, sendo utilizada para garantir a eliminação de microrganismos em instrumentos e materiais reutilizáveis. Os esterilizadores hospitalares operam com controlo rigoroso de **temperatura**, **pressão**, **tempo** e, em certos modelos, **pré-vácuo** para remoção de ar da câmara.

Paralelamente, a transformação digital e o paradigma da **Indústria 4.0** têm promovido o uso de **Digital Twins** para monitorização, simulação, diagnóstico e otimização de sistemas físicos complexos.

Este projeto propõe a criação de um Digital Twin para um **esterilizador PROHS**, com potencial de adaptação futura a outros sistemas térmicos usados na indústria.

---

## 2. Problema

Os esterilizadores são sistemas críticos e complexos, envolvendo múltiplas fases operacionais, sensores, atuadores e condições de segurança. A análise do seu funcionamento pode ser difícil quando feita apenas através do equipamento físico.

Alguns problemas típicos incluem:

- dificuldade em visualizar o comportamento global do ciclo;
- dificuldade em diagnosticar falhas intermitentes;
- ausência de uma réplica digital para teste e formação;
- necessidade de monitorização e validação contínua;
- dificuldade em reutilizar o conhecimento do domínio hospitalar em ambientes industriais.

---

## 3. Objetivos

O objetivo principal é desenvolver um **Digital Twin funcional e modular** para um esterilizador PROHS capaz de:

- representar digitalmente o comportamento do equipamento;
- monitorizar variáveis críticas do processo;
- simular ciclos de esterilização;
- detetar desvios e eventos anómalos;
- apoiar manutenção, diagnóstico e formação;
- servir de base para adaptação a sistemas industriais semelhantes.

---

## 4. Objetivos Específicos

- Modelar o ciclo de esterilização através de uma **máquina de estados**.
- Definir os principais **inputs, outputs e eventos** do sistema.
- Criar uma arquitetura em camadas inspirada em soluções industriais.
- Desenvolver visualizações do processo (estado, temperatura, pressão, vácuo).
- Simular o comportamento esperado do ciclo.
- Comparar comportamento real e comportamento simulado.
- Identificar casos de uso e perfis de utilizador.
- Organizar o projeto com metodologia orientada a requisitos e user stories.

---

## 5. Questão de Investigação / Motivação

Como pode um **Digital Twin** aplicado a um esterilizador hospitalar melhorar a **monitorização**, o **diagnóstico**, a **simulação** e a **formação**, mantendo simultaneamente uma arquitetura suficientemente genérica para futura adaptação a contextos industriais?

---

## 6. Descrição do Sistema

O sistema em estudo é um **esterilizador hospitalar a vapor saturado PROHS**, com:

- **pré-vácuo**, para remoção do ar da câmara antes da exposição ao vapor;
- **gerador de vapor integrado**;
- sensores de **temperatura**, **pressão**, **nível de água** e estado da **porta/bloqueio**;
- atuadores como **válvulas**, **bomba de vácuo**, **aquecimento** e **mecanismo de bloqueio**.

---

## 7. O que é um Digital Twin neste projeto

Neste projeto, o Digital Twin é uma **representação digital do esterilizador físico**, capaz de:

- refletir o estado atual do sistema;
- guardar histórico de ciclos;
- simular curvas de processo;
- comparar comportamento real com comportamento esperado;
- gerar alertas e apoiar análise técnica;
- servir de ferramenta de treino.

Não se trata apenas de visualização de dados, mas de um sistema que combina:

- **aquisição de dados**,
- **modelo lógico do processo**,
- **modelo funcional/térmico**,
- **motor de eventos**,
- **armazenamento histórico**,
- **interface de apoio à decisão**.

---

## 8. Arquitetura do Sistema

A arquitetura global divide-se em várias camadas:

```text
Sistema Físico
   ↓
Aquisição de Dados
   ↓
Conectividade
   ↓
Digital Twin Core
   ↓
Aplicações
   ↓
Integração / Relatórios
