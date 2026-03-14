# AWS RDS Multi-AZ Lab

Repositório do laboratório de implementação de banco de dados relacional gerenciado na AWS, realizado via Escola da Nuvem.

## 🚀 O que foi feito
* Configuração de **Security Groups** e **Subnet Groups** para isolamento de rede e alta disponibilidade.
* Provisionamento de instância **Amazon RDS (MySQL)** com replicação síncrona (**Multi-AZ**).
* Integração de uma aplicação web em **EC2** com o endpoint do banco de dados.
* Testes de persistência de dados (CRUD) em ambiente escalável e resiliente.

## 🛠️ Tecnologias
* **AWS RDS** (MySQL)
* **AWS VPC** (Networking & Security Groups)
* **AWS EC2** (Application Host)

## ⚙️ Guia de Execução
1. **Security Group:** Criado o `DB Security Group` permitindo porta `3306` apenas com origem no `Web Security Group`.
2. **Subnet Group:** Configurado com sub-redes em duas Zonas de Disponibilidade (AZs) para suporte a failover.
3. **Provisionamento RDS:** Instância `db.t3.medium` com Multi-AZ habilitado e banco de dados inicial `lab`.
4. **Conectividade:** Integração da aplicação via Endpoint do RDS utilizando credenciais de administrador.

## 💾 Comandos SQL de Referência (CRUD)
Exemplos de comandos executados pela aplicação para gerenciar o banco:

```sql
-- Criar a tabela de contatos
CREATE TABLE contacts (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100)
);

-- Inserir e Listar dados
INSERT INTO contacts (name, email) VALUES ('Nome Exemplo', 'email@exemplo.com');
SELECT * FROM contacts;
