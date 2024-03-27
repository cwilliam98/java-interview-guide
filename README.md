# Guia para entrevistas Java/Spring-boot


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
    - Herença: No Java, a herança é implementada através da utilização da palavra-chave "extends".
        ```java
        public class NomeDaClasseDerivada extends NomeDaSuperclasse {
          // atributos e métodos da classe derivada
        }

        ```
    - Encapsulamento: Em Java, o encapsulamento é implementado através do uso de modificadores de acesso e dos métodos getters e setters.
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



Fonte: [seujorge - Java: Perguntas em Entrevistas Técnicas - 1](https://www.tabnews.com.br/seujorge/java-perguntas-em-entrevistas-tecnicas-programacao-orientada-a-objetos-parte-i)
[seujorge - Java: Perguntas em Entrevistas Técnicas - 2](https://www.tabnews.com.br/seujorge/java-perguntas-em-entrevistas-tecnicas-programacao-orientada-a-objetos-parte-ii)