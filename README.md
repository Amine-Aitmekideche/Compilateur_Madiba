# Projet de Compilateur – Théorie des Langages

## Description
Ce projet académique consiste à développer un **mini compilateur** pour un langage simple appelé **Madiba**, incluant les étapes suivantes :

- **Analyse lexicale** : reconnaissance des lexèmes à partir du code source.  
- **Analyse syntaxique** : construction de l’arbre syntaxique et vérification de la grammaire.  
- **Analyse sémantique** : vérification des types, gestion des variables et symboles via une table des symboles.  

Le compilateur utilise **Lex (Flex)** pour l’analyse lexicale et **Yacc (Bison)** pour l’analyse syntaxique, avec des fichiers pour la table des symboles et une pile pour la gestion des contextes.

---

## Prérequis
Pour compiler et exécuter le projet, vous devez avoir installé :

- **GCC** ou tout compilateur C compatible
- **Flex** (Lexical Analyzer)
- **Bison** (Parser Generator)


## Compilation et Exécution
1. Générer les fichiers C à partir de Lex et Yacc :

```bash

flex lexy.l
bison -d s.y
```
Ceci produira lex.yy.c, yacc.tab.c et yacc.tab.h.

2. Compiler tous les fichiers sources :

```bash

gcc -o  main.c lex.yy.c yacc.tab.c symbol_table.c pile.c -lm
```
3. Exécuter le compilateur sur un fichier source :

```bash

./ test.txt
```
test.txt est le fichier contenant le code source écrit en langage Madiba