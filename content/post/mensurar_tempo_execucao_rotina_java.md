---
title: "Mensurar Tempo de Execução de uma rotina em Java"
date: 2023-03-07T14:12:35-03:00
tags: [development, java]
draft: false
---

```java
Instant start = Instant.now();
Thread.sleep(2000); // Força uma "parada" por 2000 ms
Instant end = Instant.now();

System.out.println(Duration.between(start, end));
```
