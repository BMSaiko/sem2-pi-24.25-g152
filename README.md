# Integrative Project – Semester 2 – Group G152 (2024/25)

**Degree:** BSc in Computer Engineering – ISEP  
**Course:** Integrative Project (PI) – 2nd Semester  
**Repository:** `sem2-pi-24.25-g152`

---

## Table of Contents
- [Project Overview](#project-overview)
- [Current Repository State](#current-repository-state)
- [Main Features & Components](#main-features--components)
- [Technologies & Requirements](#technologies--requirements)
- [Installation, Build & Execution](#installation-build--execution)
- [Repository Structure](#repository-structure)
- [MATCP & MDISC Overview](#matcp--mdisc-overview)
- [Testing & Coverage](#testing--coverage)
- [Git Workflow & Contribution](#git-workflow--contribution)
- [Documentation Guidelines](#documentation-guidelines)
- [Continuous Integration / Badges](#continuous-integration--badges)
- [Roadmap & Future Improvements](#roadmap--future-improvements)
- [Known Issues](#known-issues)
- [License & Contact](#license--contact)

---

## Project Overview
This repository hosts the codebase and documentation for the **Integrative Project (PI)** of the 2nd semester (academic year 2024/25), developed by **Group G152**.  
The project combines **software engineering principles, Agile practices (Scrum), object-oriented design, testing, and continuous integration**.

Students are expected to design, implement, and document a complete software solution, divided into sprints with corresponding artefacts and deliverables.

---

## Current Repository State
- Public repository containing the base project structure.  
- Configured with **Maven** (`pom.xml`) for dependency management and build automation.  
- Contains both **MATCP** (planning and user story notebook) and **MDISC** (application code).  
- Includes documentation folders and templates for sprint reports and technical documents.  
- The project’s entry point is defined as  
  `pt.ipp.isep.dei.esoft.project.ui.Main` in the Maven configuration.

---

## Main Features & Components
- **Main Application (MDISC)**  
  Java application with a main entry point for console-based or GUI execution.  
- **MATCP Notebook (`matcp.ipynb`)**  
  Jupyter notebook that stores user stories, backlog definitions, and sprint planning material.  
- **Documentation & Templates**  
  Located under `docs/`, containing system documentation, sprint evidence, and UML artefacts.  
- **Build System**  
  Apache Maven handles dependencies, packaging, and testing.  
- **Testing Setup**  
  JUnit + JaCoCo are supported for unit testing and coverage reporting.

---

## Technologies & Requirements
- **Java** – version 17 or higher (as per `pom.xml`)  
- **Apache Maven** 3.6 or newer  
- **Git + GitHub** – version control and issue tracking  
- **IDE** – IntelliJ IDEA / VSCode with Java plugin  
- **Jupyter Notebook** (for `matcp.ipynb`, optional)

---

## Installation, Build & Execution

### 1. Clone the repository
```bash
git clone https://github.com/BMSaiko/sem2-pi-24.25-g152.git
cd sem2-pi-24.25-g152
2. Compile and run unit tests
bash
Copiar código
mvn clean test
3. Generate documentation (optional)
bash
Copiar código
mvn javadoc:javadoc
mvn javadoc:test-javadoc
4. Create an executable JAR
Make sure the maven-assembly-plugin in pom.xml is configured with
jar-with-dependencies. Then run:

bash
Copiar código
mvn package
Result:
target/project-template-1.0-SNAPSHOT-jar-with-dependencies.jar

5. Execute the JAR
bash
Copiar código
java -jar target/project-template-1.0-SNAPSHOT-jar-with-dependencies.jar
Repository Structure
css
Copiar código
/
├── docs/                      ← Documentation, sprint evidence, and templates
│   ├── system-documentation/  ← UML, ADRs, diagrams
│   └── sprint1/…              ← Sprint folders
├── src/                       ← Java source code
│   └── main/java/pt/ipp/isep/dei/esoft/project/ui/Main.java
├── matcp.ipynb                ← MATCP notebook (user stories and planning)
├── pom.xml                    ← Maven configuration file
├── README_MATCP.md            ← MATCP-specific notes
├── .gitignore                 ← Git ignore rules
└── README.md                  ← This file
MATCP & MDISC Overview
MATCP (Planning Layer)
Contains user stories, acceptance criteria, priorities, and backlog items.

Implemented using a Jupyter Notebook (matcp.ipynb).

MDISC (Implementation Layer)
The executable application built in Java.

Source code located in src/ following standard Maven structure.

Main class: pt.ipp.isep.dei.esoft.project.ui.Main.

Testing & Coverage
The pom.xml supports test execution and coverage validation using JUnit and JaCoCo.

Commands:

bash
Copiar código
mvn test jacoco:report
mvn test jacoco:check
Reports are generated under:

bash
Copiar código
target/site/jacoco/
Git Workflow & Contribution
Main branch: stable and deployable code.

Feature branches: named using the pattern
<ID>_<USname> → e.g., 1_US3_login_module.

Pull Requests: required for all merges into main, with peer review.

Commit Message Format:

makefile
Copiar código
US-15: Implement customer registration validation
Branch Rules:

Keep commits small and atomic.

Reference issues or user stories in commit messages.

Documentation Guidelines
All diagrams and technical artefacts should be stored in docs/system-documentation/.

Each sprint should include:

Sprint goal & summary

List of implemented user stories

Retrospective observations

README_MATCP.md summarises MATCP user stories and sprint progress.

Continuous Integration / Badges
You can automate builds and testing using GitHub Actions.

Example workflow: .github/workflows/maven.yml

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
Optional badges to include at the top of this README:

bash
Copiar código
[![Build Status](https://github.com/BMSaiko/sem2-pi-24.25-g152/actions/workflows/maven.yml/badge.svg)](https://github.com/BMSaiko/sem2-pi-24.25-g152/actions)
[![Coverage](https://coveralls.io/repos/github/BMSaiko/sem2-pi-24.25-g152/badge.svg?branch=main)](https://coveralls.io/github/BMSaiko/sem2-pi-24.25-g152?branch=main)
Roadmap & Future Improvements
Short Term
Validate that Main.java matches the mainClass defined in pom.xml.

Write unit tests for core functionality.

Ensure Maven build produces a fully functional executable JAR.

Mid Term
Configure GitHub Actions for continuous integration.

Improve code documentation with Javadoc and diagrams.

Integrate static analysis tools (Checkstyle, SpotBugs).

Long Term
Publish releases using GitHub Releases.

Extend project modularity or integrate APIs.

Provide an end-user guide and install script.

Known Issues
Double-check the mainClass path in pom.xml – incorrect configuration will cause packaging failure.

Ensure Java version matches the build environment.

MATCP notebook may need updating each sprint.

License & Contact
License: specify your license (e.g., MIT / Apache 2.0).

Team Members (example format):

Name	Role	Responsibilities
[Name 1]	Scrum Master	Coordination & Documentation
[Name 2]	Developer	Core Implementation
[Name 3]	QA Engineer	Testing & CI
[Name 4]	DevOps	Automation & Integration

Contact: open a GitHub Issue or email your team representative.

Credits
This project was developed as part of the Integrative Project – Semester 2 (2024/25) at ISEP,
following the Agile Scrum framework with continuous assessment through sprints.
