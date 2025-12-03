Aqui está um **README.md profissional, organizado e pronto para colocar no GitHub** para o seu projeto.
Fiz no formato ideal para repositórios, com explicação do sistema, funcionalidades, como compilar e rodar, estrutura do arquivo CSV, e tecnologias usadas.

---

# 📘 Sistema de Cadastro de Clientes — Oficina Mecânica

Este projeto implementa um **sistema completo de cadastro de clientes** para uma oficina mecânica automotiva, utilizando **C** e uma **lista duplamente encadeada** para armazenar os registros em memória, além de **persistência em arquivo CSV**.

O sistema permite **cadastrar, editar, navegar, buscar e remover clientes**, mantendo os dados salvos automaticamente em disco.

---

## 🚀 Funcionalidades

✔️ **Cadastro de clientes**
✔️ **Edição completa** ou parcial dos dados
✔️ **Remoção individual ou total**
✔️ **Busca por nome (case-insensitive)**
✔️ **Navegação pelos clientes usando setas ← e →**
✔️ **Leitura e gravação automática em arquivo CSV**
✔️ **Lista duplamente encadeada (prev/next)**
✔️ **Campos com suporte a aspas no CSV**
✔️ **Compatibilidade Windows / Linux**

---

## 🛠️ Estrutura dos Dados

Cada cliente contém:

* Nome
* Data de cadastro
* Telefone
* Email
* Modelo do carro
* Cor do carro
* Placa
* Descrição do(s) serviço(s) realizado(s)

Todos os registros são armazenados em uma **lista duplamente encadeada**:

```c
typedef struct ElementoLista {
    char nome[MAX_NOME];
    char dataCadastro[MAX_DATA];
    char telefone[MAX_TELEFONE];
    char email[MAX_EMAIL];
    char modeloCarro[MAX_MODELO];
    char corCarro[MAX_COR];
    char placaCarro[MAX_PLACA];
    char servicoRealizado[MAX_SERVICO];

    struct ElementoLista* proximo;
    struct ElementoLista* anterior;
} ElementoLista;
```

---

## 📁 Persistência — Arquivo CSV

O sistema grava automaticamente todos os registros no arquivo:

```
clientes_oficina.csv
```

Com o seguinte formato:

```
"Nome";"DataCadastro";"Telefone";"Email";"ModeloCarro";"CorCarro";"PlacaCarro";"Servico"
```

As aspas internas são escapadas corretamente (`""`).

---

## 💻 Como compilar

No **Linux/macOS**:

```bash
gcc -o oficina main.c
```

No **Windows** (MinGW):

```bash
gcc -o oficina.exe main.c
```

---

## ▶️ Como executar

No Linux:

```bash
./oficina
```

No Windows:

```bash
oficina.exe
```

---

## 📜 Menu Principal

```
-----------------------------------
         Oficina ESPARTANOS!
-----------------------------------
1. Exibir lista de clientes
2. Inserir cliente
3. Buscar e exibir cliente
4. Remover lista completa de clientes
5. Percorrer lista de clientes (setas)
6. Editar ou Remover cliente (buscar)
0. Sair
```

---

## 🔧 Tecnologias Utilizadas

* Linguagem C
* Lista duplamente encadeada
* Manipulação de arquivos CSV
* Funções de utilidade (fgets seguro, limpeza de tela, parser CSV)
* Suporte multi-plataforma (Windows/Linux)

---

## 📌 Observações

* O sistema salva **automaticamente** após inserir, editar ou remover.
* Navegação por setas funciona totalmente no Windows; no Linux é feita via `getchar()`, podendo requerer termios para suporte completo.

---

## 🧑‍💻 Autor

Projeto desenvolvido para fins acadêmicos na disciplina de **Estruturas de Dados I**.

