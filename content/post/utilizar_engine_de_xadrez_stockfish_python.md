---
title: "Utilizar a engine de xadrez stockfish com Python"
date: 2023-03-06T08:44:54-03:00
tags: [development, python, chess, stockfish]
draft: false
---

## Instalar a *engine* Stockfish no Debian/Ubuntu

```bash
sudo apt install stockfish
```

## Verificar o caminho de aonde a *engine* foi instalada

```bash
which stockfish
```

## Instalar a interface Stockfish para Python

```bash
pip install stockfish
```

## *Script* para testar se tudo foi instalado e configurado corretamente

```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-

from stockfish import Stockfish

stockfish = Stockfish(path="/usr/games/stockfish")
print(stockfish.get_board_visual())
stockfish.set_position(["e2e4", "e7e6"])
print(stockfish.get_board_visual())
```

