#clinica (script do banco de dados)

CREATE TABLE especialidade(
    id INTEGER AUTO_INCREMENT PRIMARY KEY,
    descricao VARCHAR(100) NOT NULL,
    sigla CHAR(3) NOT NULL
) engine INNODB;

CREATE TABLE medico(
    id_medico INTEGER AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    cpf VARCHAR(11) NOT NULL,
    cep VARCHAR(8) NOT NULL,
    endereco VARCHAR(100) NOT NULL,
    numero CHAR(10) NOT NULL,
    bairro VARCHAR(60) NOT NULL,
    cidade VARCHAR(80) NOT NULL,
    estado CHAR(2) NOT NULL,
    CRM VARCHAR(20) NOT NULL,
    salario DECIMAL(12,2) NOT NULL,
    celular VARCHAR(15) NOT NULL,
    cod_esp INTEGER REFERENCES especialidade(id)
   ) ENGINE INNODB;

CREATE TABLE paciente(
    id integer AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    cep VARCHAR(8),
    endereco VARCHAR(100),
    numero CHAR(10),
    complemento VARCHAR(50),
    bairro VARCHAR(50),
    cidade VARCHAR(80),
    estado CHAR(2),
    cpf VARCHAR(11) NOT NULL,
    rg VARCHAR(9) NOT NULL,
    telefone VARCHAR(15),
    celular VARCHAR(15) NOT NULL,
    email VARCHAR(100)
    ) engine INNODB;

CREATE TABLE funcao (
    id integer  AUTO_INCREMENT PRIMARY KEY,
    descricao VARCHAR(100)
    ) engine INNODB;
        
CREATE TABLE enfermeiro(
    matricula integer AUTO_INCREMENT PRIMARY KEY,nome VARCHAR(100) NOT NULL,
    cep VARCHAR(8) NOT NULL,
    endereco VARCHAR(100) NOT NULL,
    numero CHAR(10) NOT NULL,
    bairro VARCHAR(50) NOT NULL,
    cidade VARCHAR(80) NOT NULL,
    estado CHAR(2) NOT NULL,
    cpf VARCHAR(11) NOT NULL,
    rg VARCHAR(9) NOT NULL,
    telefone VARCHAR(15) NOT NULL,
    celular VARCHAR(15) NOT NULL,
    email VARCHAR(100) NOT NULL,
    salario numeric (12,2) NOT NULL,
    turno_trabalho varchar(15) NOT NULL,
    id_funcao integer REFERENCES função (id)
    ) engine INNODB