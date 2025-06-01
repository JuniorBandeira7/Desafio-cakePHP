#   Passo a passo para rodar a aplicação:

## 1 Ter os pré-requisitos instalados
- PHP

- Composer

- Banco de Dados MySQL

- Servidor Web (xampp, wampp ou similar)

## 2 Baixar ou clonar o projeto.

## 3 Instalar as dependências

Na pasta raiz do projeto execute:

```bash
composer install
```

## 4 Configurar o banco de dados

No arquivo config/app_local.php edite as credenciais de acesso ao banco:

```bash
'Datasources' => [
    'default' => [
        'host' => 'localhost',
        'username' => 'seu_usuario',
        'password' => 'sua_senha',
        'database' => 'nome_do_banco',
        ...
    ],
],
```

## 5 Criar as tabelas 

```bash
CREATE TABLE Categories (
  id int NOT NULL AUTO_INCREMENT,
  name varchar(255) NOT NULL,
  description text NOT NULL,
  PRIMARY KEY (id)
);

CREATE TABLE Products (
  id int NOT NULL AUTO_INCREMENT,
  name varchar(255) NOT NULL,
  description text NOT NULL,
  price decimal NOT NULL,
  category_id int NOT NULL,
  PRIMARY KEY (id),
  FOREIGN KEY (category_id) REFERENCES Categories(id)
);
```

## 6 Rodar o servidor

```bash
bin/cake server
```
