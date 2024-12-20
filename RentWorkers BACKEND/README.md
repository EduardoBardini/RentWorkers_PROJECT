# RentWorkers 💻

## 📌 Índice
- [Tecnologias](#technologies)   
- [Endpoints da API](#routes)  
- [Colaboradores](#colab)  
- [Contribua](#contribute)  

---

## ✨ Sobre
**RentWorkers** é uma plataforma simples que conecta profissionais qualificados a clientes em busca de seus serviços.

---

## 💻 Tecnologias
- **Java**  
- **Dbeaver**  
- **Spring Boot**
 

---

## Endpoints da API

- Link swagger: http://localhost:8080/swagger-ui/index.html#/


### 🔧 Pré-requisitos
- [Spring Boot Extension Pack](https://github.com/)  
- [Extension Pack for Java](https://github.com/)  
- [Dbeaver](https://github.com/)  

-- BANCO DE DADOS -- 

-- TABELA USUARIO:
  CREATE TABLE usuario (
	id_usuario bigserial NOT NULL,
	username varchar(50) NOT NULL,
	email varchar(70) NOT NULL,
	password varchar(250) NOT NULL,
	telefone varchar(50) NULL,
	cep varchar(40) NOT NULL,
	tipo_usuario varchar(20) NOT NULL,
	especialidade varchar(50) NULL,
	CONSTRAINT usuario_email_key UNIQUE (email),
	CONSTRAINT usuario_pkey PRIMARY KEY (id_usuario),
	CONSTRAINT usuario_telefone_key UNIQUE (telefone)
);
-- TABELA TRABALHO_SOLICITADO:
  CREATE TABLE trabalho_solicitado (
	id_trabalho_solicitado bigserial NOT NULL,
	id_usuario bigserial NOT NULL,
	id_cliente bigserial NULL,
	id_trabalhador bigserial NULL,
	tipo varchar(50) NULL,
	valor numeric(10, 2) NULL,
	localizacao varchar(100) NULL,
	descricao varchar(300) NULL,
	status bool NULL,
	CONSTRAINT trabalho_solicitado_pkey PRIMARY KEY (id_trabalho_solicitado)
);

-- TABELA AVALIACAO: 
  CREATE TABLE avaliacao (
	id_avaliacao bigserial NOT NULL,
	id_usuario bigserial NOT NULL,
	nota_avaliacao numeric(10, 2) NULL,
	texto_avaliativo varchar(250) NULL,
	id_trabalhador bigserial NOT NULL,
	CONSTRAINT avaliacao_pkey PRIMARY KEY (id_avaliacao)
  );

 -- avaliacao chaves estrangeiras

 ALTER TABLE public.avaliacao ADD CONSTRAINT avaliacao_id_usuario_fkey FOREIGN KEY (id_usuario) REFERENCES usuario(id_usuario);
 ALTER TABLE public.avaliacao ADD CONSTRAINT id_trabalhador FOREIGN KEY (id_trabalhador) REFERENCES usuario(id_usuario);

----------------

### 🛠️ Clonagem

```bash

git clone https://github.com/EduardoBardini/RentWorkers_PROJECT.git

cd RentWorkers_PROJECT

npm install

npm run dev

````

