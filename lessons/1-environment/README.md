# 1. Introducción e instalación

## Índice

[0. Prerrequisitos](#0-prerrequisitos)  
[1. Conceptos básicos](#1-conceptos-basicos)  
[2. Hola mundo](#2-hola-mundo)

## 0. Prerrequisitos

- Navegador Web: Chrome, Firefox, Edge, etc.
- Consola/Terminal: PowerShell, Git Bash, etc.
- Visual Studio Code: [https://code.visualstudio.com/](https://code.visualstudio.com/)
- Node.js / npm: [https://nodejs.org/es/download](https://nodejs.org/es/download)
- Git: [https://git-scm.com/download/](https://git-scm.com/download/)
- Extensión YAML: [https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml)

## 1. Conceptos básicos

- Workflow: Procedimiento automatizado que se añade a un repositorio de Github.
- Job: Conjunto de steps que se ejecutan en un runner de nuestro proceso.
- Step: Tarea individual que puede ejecutar comandos dentro de un job.
- Action: Comandos de ejecución del proceso, ejecutados en un step para crear un job.

## 2. Hola mundo

El primer paso para empezar a usar GitHub Actions (GHA) es crear la carpeta `.github/workflows/`, que albergará los workflows a realizar en forma de ficheros YAML.

Ejemplo ( `hw.yml` ):

    name: Hello World example

    on:
      push:
        branches:
          - main

    jobs:
      hello_world:
        runs-on: ubuntu-18.04
        steps:
          - name: Mostrar mensaje
            run: |
              echo "Hola mundo!"
          - name: Mostrar fecha
            run: date
          - run: ls -l
