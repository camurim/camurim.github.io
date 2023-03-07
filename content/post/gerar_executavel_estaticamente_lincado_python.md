---
title: "Gerar Executável Estaticamente Lincado de um script Python"
date: 2023-03-07T11:31:58-03:00
tags: [development, python, python3, linux, ubuntu, debian]
draft: false
---

## Motivação

Este processo permite executar um programa Python em um ambiente que não possua o próprio Python ou alguns dos pacotes necessários para sua execução.

## Processo de instalação dos componentes necessário

### Instalar o `pyinstaller`
```bash
pip install pyinstaller
```

### Instalar o `staticx`
```bash
sudo apt update && sudo apt install binutils patchelf
pip install patchelf-wrapper
pip install scons
git clone https://github.com/JonathonReinhart/staticx
cd staticx
scons
sudo python setup.py install
```

## Geração do executável estaticamente lincado

### Gerar executável com `pyinstaller`
```bash
pyinstaller --clean --hidden-import psycopg -F meu_script.py
```

### Tornar o executável estático
```bash
cd dist
staticx meu_script meu_script_st
```

