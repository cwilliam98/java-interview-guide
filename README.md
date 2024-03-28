# Guia para entrevistas Java/Spring-boot

# Java

- **Cite um cenário simples onde é possível usar classes e/ou métodos abstratos.**
    - Classes e métodos abstratos são uteis onde pode existir uma hierarquia de classes que compartilham comportamentos comuns, mas possuem também comportamentos específicos. Como exemplo simples, podemos citar uma aplicação que trabalha com diferentes formas geométricas, círculos, quadrados, tríangulos.

- **Qual a função da palavra reservada ``static`` e ``final``?**
    - A palavra reservada `static` permite criar variáveis ou métodos que pertence a classe em si e não a cada instância da classe. No caso de variáveis caso uma instância altere o valor dela, esse valor será refletido para todas outras instâncias, no caso dos métodos não é necessário criar uma instância da classe para acessá-lo.
    - Já o uso da palavra reservada `final` podemos dividir o funcionamento dela entre classes, métodos e variáveis.
        - Variáveis: Significa que o valor atribuído não pode ser alterado.
        - Métodos: Significa que o método não pode ser sobscrito nas subclasses.
        - Classes: Significa que a classe não pode ser estendida por outras classes.
- **Qual é o uso para cada um desses itens da Streams APIs: ``filter``, ``map``, ``forEach``**
    - ``filter``: recebe um predicado (uma função que retorna um valor booleano) e retorna um stream contendo apenas os elementos que satisfazem o predicado. Exemplo: filtrar uma lista de números e retornar apenas os números pares.
    - ``map``: recebe uma função que transforma um elemento em outro e retorna um stream contendo os elementos resultantes da aplicação da função a cada elemento do stream original. Exemplo: mapear uma lista de objetos para uma lista contendo apenas um atributo desses objetos.
    - ``forEach``: executa uma ação (um Consumer) em cada elemento do stream, sem retornar nenhum resultado. É útil para efeitos colaterais, como imprimir valores na tela ou atualizar objetos externos.

- **Quais são os pilares da Orientação a Objetos**
    - Abstração: A abstração é alcançada através da criação de classes e objetos que representam entidades ou conceitos do mundo real. A abstração permite que um objeto seja representado de forma simples e coesa, sem detalhes desnecessários, tornando mais fácil a compreensão e o uso do objeto. 
    - Encapsulamento: O encapsulamento é a prática de ocultar a implementação interna de um objeto e fornecer uma interface pública para acesso a ele. Através do encapsulamento, os detalhes internos de um objeto ficam ocultos e protegidos, impedindo o acesso direto a eles por outros objetos e garantindo que a manipulação do objeto seja feita de forma segura e consistente.
    - Herança: A herança é um mecanismo que permite que uma classe herde características e comportamentos de outra classe já existente, criando uma relação de "é um". Isso significa que uma classe derivada herda todos os atributos e métodos da classe base, além de poder adicionar novos atributos e métodos ou modificar os já existentes. A herança é usada para criar hierarquias de classes, evitando a duplicação de código e permitindo a criação de classes mais especializadas.
    - Polimorfismo: O polimorfismo é a capacidade de objetos de diferentes classes serem tratados de forma uniforme, permitindo que um método de uma classe possa ser utilizado por objetos de classes diferentes. Isso é possível porque as classes derivadas herdam os métodos da classe base, mas podem ter comportamentos diferentes. O polimorfismo é usado para criar código flexível e genérico, que pode lidar com diferentes tipos de objetos sem precisar de tratamento especial para cada um deles.

- **Cite um exemplo de utilização de Herança e Encapsulamento.**
    - Herença: No Java, a herança é implementada através da utilização da palavra-chave ``extends``.
        ```java
        public class NomeDaClasseDerivada extends NomeDaSuperclasse {
          // atributos e métodos da classe derivada
        }

        ```
    - Encapsulamento: Em Java, o encapsulamento é implementado através do uso de modificadores de acesso e dos métodos ``getters`` e ``setters``.
        ```java
        public class ContaBancaria {

            private double saldo;

            public double getSaldo() {
                return saldo;
            }

            public void depositar(double valor) {
                saldo += valor;
            }

            public void sacar(double valor) {
                saldo -= valor;
            }

        }

        ```
- **Qual a diferença entre sobrecarga e sobrescrita de métodos ?**
    - A **sobrecarga** de métodos em Java ocorre quando uma classe tem dois ou mais métodos com o mesmo nome, mas com assinaturas de parâmetros diferentes. Nesse caso, o compilador Java determina qual método deve ser chamado com base nos argumentos fornecidos no momento da chamada do método
    - Já a **sobrescrita** de métodos em Java ocorre quando uma subclasse fornece uma implementação específica de um método que já é definido em sua superclasse. Nesse caso, a assinatura do método na subclasse deve ser exatamente a mesma que na superclasse (mesmo nome, mesma lista de parâmetros e mesmo tipo de retorno). O objetivo é permitir que a subclasse substitua o comportamento padrão do método em sua superclasse por um comportamento específico à subclasse.

- **Qual a diferença entre _checked_ e _unchecked exceptions_ ?**
    - As _checked exceptions_ são exceções que podem ocorrer durante a execução de um programa, mas que podem ser previstas e tratadas pelo programador. Essas exceções devem ser declaradas na assinatura do método que as lança, usando a palavra-chave ``throws``. Além disso, se um método lança uma _checked exception_, qualquer método que o chame deve lidar com a exceção, seja capturando-a com um bloco try-catch ou propagando-a com a palavra-chave ``throws``.

        - Exemplos de _checked exceptions_ incluem ``IOException``, ``FileNotFoundException`` e ``SQLException``.
    - As _unchecked exceptions_ são exceções que ocorrem durante a execução de um programa, mas que não podem ser previstas ou tratadas pelo programador. Essas exceções não pre   cisam ser declaradas na assinatura do método que as lança e não precisam ser tratadas ou propagadas.
        - Exemplos de unchecked exceptions incluem ``NullPointerException``, ``ArrayIndexOutOfBoundsException`` e ``IllegalArgumentException``.


# Spring Boot
- **Como você definiria o Spring Boot?**
    - Spring Boot é um framework que facilita a criação de aplicações Java autônomas, com a vantagem de minimizar a configuração manual. Ele é baseado no Spring Framework e utiliza a configuração por convenção, com o objetivo de acelerar o processo de desenvolvimento de aplicações. O Spring Boot inclui uma série de recursos prontos para uso, como servidores embutidos, configuração automática de componentes, autoconfiguração, monitoramento, entre outros.
- **Qual a finalidade do uso da annotation ``@Service`` ?**
    - A anotação ``@Service`` é usada em classes para indicar que ela possui uma função de serviço, ou seja, ela contém a lógica de negócios da aplicação. Essa anotação é uma especialização da anotação ``@Component`` e é usada para tornar mais clara a intenção do desenvolvedor.
    Quando uma classe é anotada com ``@Service``, o Spring a registra como um bean gerenciado pelo container e a torna disponível para ser injetada em outras classes que a utilizam.
- **Qual a difenrença entre @Service e @Component ?**
    - Ambas as anotações, ``@Service`` e ``@Component``, são usadas para indicar que uma classe é um componente gerenciado pelo Spring. A diferença é que ``@Service`` é uma especialização de ``@Component`` e é usada para identificar serviços na camada de negócios da aplicação.
- **Qual a finalidade da annotation ``@Repository`` ?**
    - A annotation ``@Repository`` é uma anotação do Spring Framework que indica que a classe é um repositório, ou seja, é responsável pela persistência e recuperação de dados. Essa anotação é normalmente usada em conjunto com outras anotações de persistência, como ``@Autowired``, ``@Transactional``, ``@PersistenceContext``, entre outras.
- **Qual a finalidade da annotation ``@Autowired`` ?**
    - A annotation ``@Autowired`` é utilizada no Spring Framework para realizar a injeção de dependências automaticamente. Isso significa que o Spring procura por um bean correspondente ao tipo da variável a ser injetada e a instância automaticamente, evitando que o desenvolvedor tenha que fazer isso manualmente.
- **Pra que serve a annottion ``@Configuration`` ?**
    - A annotation ``@Configuration`` é utilizada para indicar que uma classe contém definições de beans que devem ser processadas pelo contêiner Spring. Em outras palavras, é utilizada para marcar uma classe como uma classe de configuração para o Spring. Essa annotation pode ser usada em conjunto com outras annotations, como ``@Bean``, ``@ComponentScan`` e ``@Import``, para definir beans e outras configurações necessárias para a aplicação. Através da annotation ``@Configuration`` é possível definir e personalizar configurações, como banco de dados, segurança, cache, entre outros.

# Testes

- **O que são testes unitários ?**
    - Testes unitários são uma técnica de teste de software que consiste em isolar e testar individualmente unidades de código, como métodos ou funções. Essas unidades são testadas para garantir que produzam o resultado esperado e funcionem corretamente em diferentes cenários. Os testes unitários são escritos pelos desenvolvedores durante o processo de desenvolvimento e são executados automaticamente para detectar erros e garantir que as mudanças de código não afetem negativamente o restante do sistema. Eles são importantes para garantir a qualidade do código, facilitar a manutenção e aumentar a confiança na entrega de software.

- **Pra que serve o Junit ?**
    - O JUnit é um framework de teste de software para a linguagem de programação Java. Ele é usado para escrever e executar testes automatizados de unidades (unit tests) para garantir que o código esteja funcionando corretamente.
    O framework fornece uma estrutura para escrever testes de forma organizada e automatizada, e também fornece recursos para assertivas (verificações) de resultados esperados, execução de testes em paralelo, entre outros recursos que facilitam a criação e manutenção de testes de software.
- **Pra que serve o Mockito ?**
    - Com o Mockito, é possível criar objetos falsos (mocks) para as classes que estão sendo testadas e simular o comportamento de métodos específicos ou comportamentos complexos de objetos reais que não são facilmente reproduzidos em um ambiente de teste. Além disso, o Mockito também permite verificar se determinados métodos foram chamados ou não, bem como a ordem em que foram chamados.
- **Qual a finalidade da annotation ``@Mock`` ?**
    - A anotação ``@Mock`` é usada na biblioteca Mockito para criar um objeto simulado (mock) de uma classe ou interface em um teste. Ela permite simular o comportamento de um objeto real durante a execução do teste, sem a necessidade de criar uma instância real da classe.
- **Qual a finalidade da annotation ``@InjectMocks`` ?**
    - A annotation ``@InjectMocks`` é usada em testes de unidade com o framework Mockito para injetar automaticamente instâncias de objetos anotados com ``@Mock`` em objetos que são instâncias da classe sendo testada.

# Boas práticas de desenvolvimento

- Cite algumas boas práticas na escrita de código limpo:
Nomes significativos: Utilizar nomes significativos para variáveis, métodos e classes ajuda a tornar o código mais legível e fácil de entender.

    - Funções pequenas e bem definidas: É importante criar funções que tenham apenas uma responsabilidade, sejam fáceis de entender e possam ser facilmente reutilizáveis em outros lugares do código.

    - Comentários claros e concisos: Comentários devem ser usados apenas para explicar o que não é óbvio no código. É importante que sejam claros e concisos e não poluam o código com informações desnecessárias.

    - Código bem formatado: Código bem formatado é mais fácil de ler e entender. Utilizar espaços em branco, indentação e padrões de formatação ajuda a tornar o código mais limpo e organizado.

    - Testes automatizados: Testes automatizados são essenciais para garantir a qualidade do código e reduzir a ocorrência de bugs. Eles também ajudam na manutenção do código, pois permitem verificar se as alterações realizadas não impactaram outras partes do sistema.  




Fonte: [seujorge - Java: Perguntas em Entrevistas Técnicas - 1](https://www.tabnews.com.br/seujorge/java-perguntas-em-entrevistas-tecnicas-programacao-orientada-a-objetos-parte-i)

[seujorge - Java: Perguntas em Entrevistas Técnicas - 2](https://www.tabnews.com.br/seujorge/java-perguntas-em-entrevistas-tecnicas-programacao-orientada-a-objetos-parte-ii)

[seujorge - Java: Perguntas em Entrevistas Técnicas - 3](https://www.tabnews.com.br/seujorge/java-perguntas-em-entrevistas-tecnicas-programacao-orientada-a-objetos-parte-iii)

[seujorge - Boas Práticas em Programação - S.O.L.I.D. & Clean Code: Perguntas em Entrevistas Técnicas](https://www.tabnews.com.br/seujorge/boas-praticas-em-programacao-s-o-l-i-d-e-clean-code-perguntas-em-entrevistas-tecnicas)

[seujorge - Testes Automatizados: Perguntas em Entrevistas Técnicas](https://www.tabnews.com.br/seujorge/testes-automatizados-perguntas-em-entrevistas-tecnicas)