# 📚 Gestão de Biblioteca Escolar (POO)

Uma aplicação de console robusta desenvolvida em C# para o gerenciamento completo do acervo, usuários e empréstimos de uma biblioteca escolar. Este projeto foi construído com forte ênfase em **Programação Orientada a Objetos (POO)**, aplicando conceitos avançados de arquitetura limpa e separação de responsabilidades (SRP).

## ✨ Funcionalidades

* **Gestão de Usuários:** Cadastro seguro com validação de campos obrigatórios e garantia de unicidade de matrícula. Suporte à atualização de dados (como e-mail).
* **Gestão de Acervo (Polimorfismo):** Cadastro dinâmico de `Livros` e `Revistas`, com regras específicas de negócio (prazos e multas diferenciados) herdadas de uma classe abstrata comum.
* **Empréstimos Inteligentes:** Validação rigorosa de regras de negócio (limite máximo de 3 empréstimos ativos por usuário, bloqueio de itens já emprestados).
* **Simulador de Empréstimos e Devoluções:** Módulo de testes integrado e sobrecarga de construtores que permite simular datas customizadas tanto para a retirada quanto para devoluções futuras. Isso projeta cálculos de prazos e multas para casos de uso atípicos, sem corromper o banco de dados em memória.
* **Relatórios e Consultas:** Geração de tabelas formatadas e dinâmicas (utilizando LINQ) para listagem de acervo, usuários, empréstimos ativos e consolidação financeira das multas geradas.

## 🚀 Tecnologias e Conceitos Utilizados

**Linguagem & Framework:**
* C#
* .NET 8.0 (Console Application)

**Engenharia de Software & Boas Práticas:**
* **POO Avançada:** Uso prático de Classes Abstratas, Interfaces (`IEmprestavel`), Herança e Polimorfismo para tratar diferentes tipos de materiais de forma genérica.
* **Encapsulamento Restrito:** Proteção rigorosa do estado interno dos objetos (ex: as datas e o status de disponibilidade só mudam através de métodos controlados na classe `Emprestimo` e `MaterialBiblioteca`).
* **Separação de Responsabilidades (SRP):**
  * `Menu.cs`: Responsável exclusivo pela camada de interface com o usuário (I/O, validações de conversão com *TryParse*, tratamento de strings vazias).
  * `Biblioteca.cs`: Atua como a camada de serviço e controlador, gerenciando as listas de dados e orquestrando o fluxo das regras de negócio.
  * `Program.cs`: Foca apenas no laço principal de execução e roteamento do sistema.
* **Design Patterns & Clean Code:** Aplicação de *Early Return* (retorno antecipado) para evitar aninhamento excessivo de blocos `if/else`, garantindo um código muito mais legível.

---

## ⚙️ Como Executar o Projeto

Como a aplicação foi desenvolvida em .NET, é necessário ter o [SDK do .NET](https://dotnet.microsoft.com/pt-br/download) instalado em sua máquina.

1. **Clone este repositório:**
   ```bash
   git clone https://github.com/valdirneto34/GestaoBiblioteca-POO.git
   cd GestaoBiblioteca-POO
   ```

2. **Compile e execute a aplicação:**
   Estando na raiz do projeto (onde está localizado o arquivo `.csproj`), execute o seguinte comando no terminal:
   ```bash
   dotnet run
   ```

---

## 📁 Estrutura do Projeto

* `Program.cs`: Ponto de entrada da aplicação, contendo o loop do menu principal.
* `Menu.cs`: Classe utilitária estática para entrada e saída de dados no console, garantindo validações anti-falhas durante a digitação.
* `Biblioteca.cs`: Classe central que armazena os dados em memória através de listas genéricas e orquestra as operações principais do domínio.
* `Usuario.cs`: Entidade de domínio representando os leitores da biblioteca.
* `MaterialBiblioteca.cs`: Entidade base e classes filhas (`Livro` e `Revista`) do acervo, implementando regras polimórficas de negócio.
* `Emprestimo.cs`: Classe associativa que une Usuários e Materiais, concentrando toda a inteligência e cálculos de datas, atrasos e multas.

---

## 👨‍💻 Autores

**[Valdir Neto](https://github.com/valdirneto34)** & **[Patrícia Silva](https://github.com/Silv-Patricia)**

Estudantes de Sistemas de Informação no IFMG-SJE.