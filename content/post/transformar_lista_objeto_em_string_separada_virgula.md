---
title: "Transformar Lista de Objetos em String Separada por Virgulas"
date: 2023-03-07T12:37:24-03:00
tags: [development, java, lambda]
draft: false
---

```java
import java.util.ArrayList;
import java.util.List;
import java.util.logging.Logger;

class Pessoa {
	int id;
	String nome;
	
	public Pessoa(int id, String nome) {
		this.id = id;
		this.nome = nome;
	}
	
	public void setId(int id) {
		this.id = id;
	}
	
	public int getId() {
		return this.id;
	}
	
	public void setNome(String nome) {
		this.nome = nome;
	}
	
	public String getNome() {
		return this.nome;
	}
}

public class ListToString {
	
	final static Logger LOGGER = Logger.getLogger(ListToString.class.getName());

	public static void main(String[] args) {
		List<Pessoa> pessoaList = new ArrayList<Pessoa>() { private static final long serialVersionUID = 1L;
		{
			add(new Pessoa(1,"Carlos"));
			add(new Pessoa(2,"André"));
			add(new Pessoa(3,"Amorim"));
		}};
		
		String lista = pessoaList.stream().map(p -> p.nome.concat(", ")).reduce("",String::concat);
		lista = lista.substring(0,lista.lastIndexOf(","));
		
		LOGGER.info(lista);
	}

}
```

