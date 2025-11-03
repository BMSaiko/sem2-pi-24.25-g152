# Projeto Integrador — Grupo G152 (SEM2 PI 24/25)

**Curso:** Licenciatura em Engenharia Informática — ISEP (Degree in Informatics Engineering)  
**Disciplina:** Projecto Integrador (2.º semestre 2024/2025)  
**Repositório:** `sem2-pi-24.25-g152` — template/implementação inicial disponibilizada no repositório. :contentReference[oaicite:1]{index=1}

---

## Sumário
- [Visão Geral](#visão-geral)  
- [Estado atual do repositório](#estado-atual-do-repositório)  
- [Funcionalidades principais e componentes](#funcionalidades-principais-e-componentes)  
- [Requisitos e tecnologias](#requisitos-e-tecnologias)  
- [Instalação, build e execução](#instalação-build-e-execução)  
- [Estrutura do repositório](#estrutura-do-repositório)  
- [MATCP & MDISC — onde estão e como usar](#matcp--mdisc---onde-estão-e-como-usar)  
- [Testes & Cobertura](#testes--cobertura)  
- [Fluxo de trabalho Git / Contribuição](#fluxo-de-trabalho-git--contribuição)  
- [Sugestões de CI / Badges / Automação](#sugestões-de-ci--badges--automação)  
- [Roadmap e melhorias futuras](#roadmap-e-melhorias-futuras)  
- [Licença & Contactos](#licença--contactos)

---

## Visão geral
Este repositório é um template + implementação de suporte para o Projecto Integrador do 2.º semestre, fornecendo:
- Artefactos didácticos (templates, documentação e evidências de sprint).  
- Uma aplicação Java de exemplo com estrutura Maven.  
- Um notebook MATCP com user stories/planeamento.  
Os ficheiros principais e a organização actual do repositório foram encontrados na raiz: `pom.xml`, `matcp.ipynb`, `docs/`, `src/`. :contentReference[oaicite:2]{index=2}

---

## Estado atual do repositório
- Repositório público com uma implementação base (código Java e Jupyter notebook). :contentReference[oaicite:3]{index=3}  
- `pom.xml` já define a estrutura de build/packaging (o `mainClass` sugerido para o empacotamento no `pom.xml` é `pt.ipp.isep.dei.esoft.project.ui.Main`). Isto permite gerar um JAR “com dependências” se o `maven-assembly-plugin` for configurado. :contentReference[oaicite:4]{index=4}

---

## Funcionalidades principais e componentes
(Resumo do que existe/espera-se com base no conteúdo do repositório)
- **Aplicação MDISC/Main**: aplicação Java com interface (CLI) que pode ser iniciada a partir do `Main.java` — indicado no `pom.xml`. :contentReference[oaicite:5]{index=5}  
- **MATCP**: notebook (`matcp.ipynb`) com user stories MATCP e documentação associada — serve como base para identificação de US e planificação de sprints. :contentReference[oaicite:6]{index=6}  
- **Docs / Templates**: templates para requisitos, design, testes e artefactos de sprint (em `docs/`). :contentReference[oaicite:7]{index=7}

---

## Requisitos e tecnologias
- Java (recomenda-se Java 17+ — ajusta conforme `pom.xml`)  
- Apache Maven (3.6+) para build, testes e packaging.  
- Jupyter / JupyterLab para visualizar/editar `matcp.ipynb` (opcional).  
- IDE recomendada: IntelliJ IDEA ou VSCode com extensão Java/Maven.  
(Informação corroborada pela presença de `pom.xml`, `src` e `matcp.ipynb` no repositório). :contentReference[oaicite:8]{index=8}

---

## Instalação, build e execução

### 1) Clonar repositório
```bash
git clone https://github.com/BMSaiko/sem2-pi-24.25-g152.git
cd sem2-pi-24.25-g152
2) Build com Maven (compilar + testes)
bash
Copiar código
mvn clean test
3) Gerar JAR executável com dependências
No pom.xml está sugerida a utilização do maven-assembly-plugin para gerar um jar-with-dependencies. Se já estiver configurado, basta:

bash
Copiar código
mvn package
# Resultado em: target/project-template-1.0-SNAPSHOT-jar-with-dependencies.jar
O pom.xml aponta o Main para pt.ipp.isep.dei.esoft.project.ui.Main (ver pom.xml). Ajusta se necessário. 
GitHub

4) Executar o JAR
bash
Copiar código
java -jar target/project-template-1.0-SNAPSHOT-jar-with-dependencies.jar
5) Executar a partir da IDE
Importa o projeto como um projecto Maven e corre a classe pt.ipp.isep.dei.esoft.project.ui.Main (ou outra classe Main que exista/definas).

Estrutura do repositório (detalhada)
bash
Copiar código
/ (repo root)
├─ .idea/ or .vscode/        # IDE config (não comitar secrets)
├─ MATCP/                    # Material / exercícios MATCP (user stories)
├─ docs/                     # Documentação e templates de sprint
├─ src/                      # Código-fonte Java (package structure)
├─ matcp.ipynb               # Notebook com user stories MATCP
├─ pom.xml                   # Configuração Maven (dependências/build)
├─ README_MATCP.md           # Documento com info MATCP
└─ README.md                 # Este ficheiro
(Conteúdo visível no repositório). 
GitHub

MATCP & MDISC — onde estão e como usar
matcp.ipynb: contém as user stories e análises que a equipa deverá usar como base para as US e criterios de aceitação. Abre com Jupyter. 
GitHub

docs/system-documentation/sprint2/ (e pastas por US): contém documentação gerada por sprint e os artefactos associados. Usa essas pastas para anexar diagramas (UML), casos de uso e registos de decisão de arquitectura.

Testes & Cobertura
O pom.xml já refere objetivos comuns (mvn test, jacoco report/check). Recomenda-se:

Escrever testes JUnit para todas as classes core.

Configurar JaCoCo para gerar relatório e falhar o pipeline se cobertura < threshold (ex.: 70%).
Comandos suportados (documentados): mvn clean test, mvn test jacoco:report, mvn test jacoco:check. 
GitHub
+1

Convenções de Git / Fluxo de trabalho (recomendado)
Branch main — código estável / entregue.

Branches de trabalho: <US-ID>_<nome_curto> (ex.: 12_US3_login-module). (Já sugerido no repositório). 
GitHub

Pull Requests obrigatórios para merge em main com ao menos 1 reviewer.

Commits curtos e descritivos: US-12: Implement login validations.

Issues: utilizar GitHub Issues para bugs/tarefas e linkar PRs a issues.

Boas práticas de documentação
Atualizar docs/system-documentation/ por sprint com: diagramas de classes (UML), diagrama de sequência, decisões de arquitectura (ADR), e resultados de testes.

Preencher README_MATCP.md com sumário das user stories implementadas por sprint. 
GitHub

Sugestões de CI / Badges / Automação
Sugiro configurar GitHub Actions com os seguintes passos:

Workflow maven.yml que execute em push/PR:

mvn -B clean verify (compilar, executar testes).

Gerar relatório JaCoCo e publicar artefactos via Actions (opcional).

Badge de build (Actions) e badge de cobertura no README.md.

Se necessário, adicionar etapa de checkstyle / spotbugs para qualidade de código.

Exemplo de job básico (GitHub Actions):

yaml
Copiar código
name: Java CI

on: [push, pull_request]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Set up JDK 17
        uses: actions/setup-java@v4
        with:
          java-version: '17'
          distribution: 'temurin'
      - name: Build with Maven
        run: mvn -B clean verify
Roadmap & melhorias futuras (prioritizadas)
Curto prazo

Completar testes unitários para módulos core.

Garantir que pom.xml gera um JAR executável com Main correto. 
GitHub

Atualizar documentação em docs/ com diagramas essenciais.

Médio prazo

Integrar GitHub Actions para build/test/coverage.

Criar scripts de inicialização (ex.: start.sh) para facilitar testes locais.

Definir e documentar API/contratos (se houver módulos integráveis).

Longo prazo

Empacotar e publicar release (GitHub Releases).

Configurar deploy automatizado (se for uma aplicação com UI/serviço).

Documentação de instalação para utilizadores não-técnicos.

Known issues / pontos de atenção
Conferir se a classe pt.ipp.isep.dei.esoft.project.ui.Main existe e corresponde ao mainClass usado para empacotar o JAR — caso contrário actualizar o pom.xml. 
GitHub

Verificar compatibilidade da versão Java local com a definida no pom.xml.

Licença
Indica a licença do projecto (ex.: MIT, Apache-2.0). Se ainda não houver LICENSE, adiciona um ficheiro LICENSE com a licença escolhida.

Contactos / Contribuidores
Equipa: preencher nomes e responsabilidades no README (Team Members & Task Distribution). 
GitHub

Para dúvidas ou issues: abrir um Issue no repositório.

Créditos / Referências
Ficheiros base e templates presentes no repositório. 
GitHub

Informação de build e mainClass obtida do pom.xml. 
GitHub
