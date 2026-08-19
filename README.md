# Concessionária (Java)

Sistema em **Java** para gerenciamento de uma concessionária de veículos, executado via linha de comando (CLI). Permite cadastrar clientes, veículos (carros e motos) e registrar vendas, com persistência dos dados em arquivos serializados (`.ser`).

## Funcionalidades

- **Clientes**: cadastro e gerenciamento de clientes
- **Veículos**: cadastro de carros e motos (com atributos específicos de cada tipo)
- **Vendas**: registro de vendas associando cliente e veículo
- Carga inicial de dados de exemplo ao iniciar o sistema
- Persistência local dos dados via serialização de objetos (sem necessidade de banco de dados externo)
- Registro de logs/erros em arquivo (`logs/erro.txt`)

## Tecnologias

- Java (projeto simples, sem Maven/Gradle — pensado para rodar via VS Code/JDK)
- Programação orientada a objetos (herança entre `Veiculo`, `Carro` e `Moto`)
- Padrão em camadas: `model`, `dal` (DAO), `controller`, `view`

## Estrutura do projeto

```
concessionaria/
├── src/
│   ├── App.java              # Ponto de entrada da aplicação
│   ├── model/                 # Entidades: Cliente, Veiculo, Carro, Moto, Venda
│   ├── dal/                    # DAOs responsáveis pela persistência (.ser)
│   ├── controller/              # Regras de negócio
│   ├── view/                     # Menus e interação via terminal
│   ├── util/                      # Utilitários (carga inicial de dados, logs)
│   └── dados/                      # Arquivos de persistência (.ser)
├── bin/                                # Classes compiladas
└── logs/                                # Arquivo de log de erros
```

## Modelos principais

- **Veiculo** (abstrato): marca, modelo, ano, cor, preço
  - **Carro**: adiciona número de portas
  - **Moto**: variação específica de veículo
- **Cliente**: dados do cliente
- **Venda**: associa um cliente a um veículo vendido

## Como executar

### Pré-requisitos

- JDK instalado (Java 8+)

### Via linha de comando

```bash
# Clone o repositório
git clone https://github.com/Jau9090/Concessionaria-Java.git
cd Concessionaria-Java/concessionaria/concessionaria

# Compile
javac -d bin src/App.java src/model/*.java src/dal/*.java src/controller/*.java src/view/*.java src/util/*.java

# Execute
java -cp bin App
```

### Via VS Code

1. Abra a pasta `concessionaria/concessionaria` no VS Code com a extensão *Java Extension Pack* instalada
2. Execute a classe `App.java` diretamente pelo editor

## Uso

Ao iniciar, o sistema carrega dados de exemplo e exibe um menu interativo no terminal:

```
--- Menu Principal ---
1. Clientes
2. Veículos
3. Vendas
0. Sair
```

Basta digitar o número da opção desejada para navegar pelos submenus de cadastro e consulta.

## Licença

Projeto acadêmico/pessoal, sem licença definida.
