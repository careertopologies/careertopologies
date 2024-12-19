# Topologias

[![Botão para voltar](https://img.shields.io/badge/VOLTAR-readme-white?style=for-the-badge)](./README.md)

No contexto deste framework, o termo "topologia" é usado para descrever a forma como as carreiras são estruturadas dentro de uma área. Muitas vezes referido como "ladder", "escada" ou "trilha", a topologia define os caminhos possíveis para o crescimento profissional. Não há uma única maneira de construir uma carreira em uma organização; cada área pode adotar topologias diferentes, dependendo de suas necessidades específicas.

## Modelo em Y

Esse modelo oferece dois caminhos distintos: **gestão** e **contribuição individual** (ou técnica). Em algum ponto de sua trajetória, o profissional é incentivado a escolher entre seguir a trilha de gestão ou continuar sua jornada como especialista técnico.

```mermaid
flowchart TB
    %% Definição de Subgráficos e Estilos %%
    subgraph "CHIEF LEVEL"
        style CLEVEL fill:#004d4d,stroke:#333,stroke-width:4px,color:#fff
        CLEVEL["C-LEVEL"]
    end

    subgraph "MANAGEMENT LEVEL"
        style VP fill:#4b0082,stroke:#333,stroke-width:4px,color:#fff
        style HEAD fill:#4b0082,stroke:#333,stroke-width:4px,color:#fff
        style MANAGER fill:#4b0082,stroke:#333,stroke-width:4px,color:#fff
        style LEAD fill:#4b0082,stroke:#333,stroke-width:4px,color:#fff
        VP["VP"] --> HEAD["HEAD / DIRECTOR"] --> MANAGER["MANAGER"] --> LEAD["LEAD / COORD"]
    end

    subgraph "TECHNICAL LEVEL"
        style FELLOW fill:#0066cc,stroke:#333,stroke-width:4px,color:#fff
        style DISTINGUISHED fill:#0066cc,stroke:#333,stroke-width:4px,color:#fff
        style PRINCIPAL fill:#0066cc,stroke:#333,stroke-width:4px,color:#fff
        style STAFF fill:#0066cc,stroke:#333,stroke-width:4px,color:#fff
        FELLOW["FELLOW"] --> DISTINGUISHED["DISTINGUISHED"] --> PRINCIPAL["PRINCIPAL"] --> STAFF["STAFF / SPEC"]
    end

    subgraph "BASE LEVEL"
        style SENIOR fill:#009999,stroke:#333,stroke-width:4px,color:#fff
        style MID fill:#009999,stroke:#333,stroke-width:4px,color:#fff
        style JUNIOR fill:#009999,stroke:#333,stroke-width:4px,color:#fff
        SENIOR["SENIOR"] --> MID["MID"] --> JUNIOR["JUNIOR"]
    end

    subgraph "ENTRY LEVEL"
        style INTERN fill:#808080,stroke:#333,stroke-width:4px,color:#fff
        style ASSOCIATE fill:#808080,stroke:#333,stroke-width:4px,color:#fff
        INTERN["INTERN"]
        ASSOCIATE["ASSOCIATE"]
    end

    %% Conexões entre Subgráficos %%
    CLEVEL --> VP
    CLEVEL --> FELLOW

    STAFF --> ASSESSMENT
    LEAD --> ASSESSMENT
    ASSESSMENT --> SENIOR

    JUNIOR --> INTERN
    JUNIOR --> ASSOCIATE

    %% Definição do nó ASSESSMENT %%
    style ASSESSMENT fill:#fff,stroke:#000,stroke-width:2px,color:#000
    ASSESSMENT["ASSESSMENT"]
```

## Modelo em W

O modelo em W expande a flexibilidade do Y, permitindo que profissionais técnicos também atuem na **gestão de projetos e/ou equipes**. Em outras áreas, esse modelo pode indicar um caminho de **consultoria** ou **programa**. A essência do modelo é oferecer um terceiro caminho de desenvolvimento dentro da organização, atendendo àqueles que desejam combinar habilidades técnicas com habilidades de gestão.


```mermaid
flowchart TB
    %% Definição de Subgráficos e Estilos %%
    subgraph "CHIEF LEVEL"
        style CLEVEL fill:#008080,stroke:#333,stroke-width:2px,color:#fff
        CLEVEL["C-LEVEL"]
    end

    %% Management Level %%
    subgraph "MANAGEMENT LEVEL"
        style VP_MANAGEMENT fill:#4b0082,stroke:#333,stroke-width:2px,color:#fff
        style HEAD_MANAGEMENT fill:#4b0082,stroke:#333,stroke-width:2px,color:#fff
        style MANAGER_MANAGEMENT fill:#4b0082,stroke:#333,stroke-width:2px,color:#fff
        style LEAD_MANAGEMENT fill:#4b0082,stroke:#333,stroke-width:2px,color:#fff
        VP_MANAGEMENT["VP (Management)"]
        HEAD_MANAGEMENT["HEAD / DIRECTOR"]
        MANAGER_MANAGEMENT["MANAGER"]
        LEAD_MANAGEMENT["LEAD / COORD"]
        VP_MANAGEMENT --> HEAD_MANAGEMENT --> MANAGER_MANAGEMENT --> LEAD_MANAGEMENT
    end

    %% Project/Technical-Management Level %%
    subgraph "PROJECT / TECHNICAL-MANAGEMENT LEVEL"
        style VP_PROJECT fill:#800080,stroke:#333,stroke-width:2px,color:#fff
        style HEAD_PROJECT fill:#800080,stroke:#333,stroke-width:2px,color:#fff
        style MANAGER_PROJECT fill:#800080,stroke:#333,stroke-width:2px,color:#fff
        style LEAD_PROJECT fill:#800080,stroke:#333,stroke-width:2px,color:#fff
        VP_PROJECT["VP (Project/Tech Mgmt)"]
        HEAD_PROJECT["HEAD / DIRECTOR"]
        MANAGER_PROJECT["MANAGER"]
        LEAD_PROJECT["LEAD"]
        VP_PROJECT --> HEAD_PROJECT --> MANAGER_PROJECT --> LEAD_PROJECT
    end

    %% Technical Level %%
    subgraph "TECHNICAL LEVEL"
        style FELLOW_TECHNICAL fill:#0066cc,stroke:#333,stroke-width:2px,color:#fff
        style DISTINGUISHED_TECHNICAL fill:#0066cc,stroke:#333,stroke-width:2px,color:#fff
        style PRINCIPAL_TECHNICAL fill:#0066cc,stroke:#333,stroke-width:2px,color:#fff
        style STAFF_TECHNICAL fill:#0066cc,stroke:#333,stroke-width:2px,color:#fff
        FELLOW_TECHNICAL["FELLOW"]
        DISTINGUISHED_TECHNICAL["DISTINGUISHED"]
        PRINCIPAL_TECHNICAL["PRINCIPAL"]
        STAFF_TECHNICAL["STAFF / SPEC"]
        FELLOW_TECHNICAL --> DISTINGUISHED_TECHNICAL --> PRINCIPAL_TECHNICAL --> STAFF_TECHNICAL
    end

    %% Base Level %%
    subgraph "BASE LEVEL"
        style SENIOR fill:#009999,stroke:#333,stroke-width:2px,color:#fff
        style MID fill:#009999,stroke:#333,stroke-width:2px,color:#fff
        style JUNIOR fill:#009999,stroke:#333,stroke-width:2px,color:#fff
        SENIOR["SENIOR"]
        MID["MID"]
        JUNIOR["JUNIOR"]
        SENIOR --> MID --> JUNIOR
    end

    %% Entry Level %%
    subgraph "ENTRY LEVEL"
        style INTERN fill:#808080,stroke:#333,stroke-width:2px,color:#fff
        style ASSOCIATE fill:#808080,stroke:#333,stroke-width:2px,color:#fff
        INTERN["INTERN"]
        ASSOCIATE["ASSOCIATE"]
    end

    %% Conexões entre os níveis principais %%
    CLEVEL --> VP_MANAGEMENT
    CLEVEL --> VP_PROJECT
    CLEVEL --> FELLOW_TECHNICAL

    %% Conexão correta do ASSESSMENT %%
    ASSESSMENT["ASSESSMENT"]
    style ASSESSMENT fill:#ffffff,stroke:#000000,stroke-width:2px,color:#000
    LEAD_MANAGEMENT --> ASSESSMENT
    LEAD_PROJECT --> ASSESSMENT
    STAFF_TECHNICAL --> ASSESSMENT
    ASSESSMENT --> SENIOR

    %% Conexões dos níveis inferiores %%
    JUNIOR --> INTERN
    JUNIOR --> ASSOCIATE
```

## Modelo em Rede

No modelo em rede, a carreira é mais fluida, permitindo que a pessoa **transite entre diferentes funções ou áreas** com base em seu engajamento e performance. Essa abordagem oferece flexibilidade para explorar e desenvolver habilidades em múltiplas áreas, promovendo um crescimento mais dinâmico.

![modelo em rede](./assets/careertopologies-model-n.png)

## Futuro

Esses modelos são apenas algumas das formas de estruturar o desenvolvimento de carreira. No desenvolvimento deste framework, serão adotados alguns padrões e aprofundamentos para cada um desses modelos, explorando como eles podem se adaptar a diferentes contextos organizacionais na próxima versão.
