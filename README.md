# Prova-2

## Classe AppUso:
  
  tem opcao para gerente fazer login e maneger sistema de acordo com as opcoes disponiveis.
  Aqui fica a funcão main e obtem a instancia do sistema atraves de padrao "Singleton";
  
  ##### Motivação
  Serve simplesmente como interface entre usuário e sistema.  
  
  ##### Vantagem  
  Ajuda-nos a manipular o sistema com mais facilidade.  
  
  
## Classe Sistema:  
  - Métodos:  
    - adicionarEmpregado: adiciona empregado especificando se é gerente;  
                        se empregado normal especifica tipo (horista, assalariado, comissionado0);  
                        
    - removerEmpregado: remover empregado atravez de ID unico;
    
    - lancarCartaoPonto: recebe um ID e seta a hora da entra ou saida na ListCartao deste;
     
    - lancarResultadoVenda: recebe um ID e adicionado a List de venda e tambem List associado ao empregado;
    
    - lancarTaxa: este a associa taxa de servico ao empregado atravez de ID;
    
    - alterarDetalhes: recebe o ID e altera os atributos necessariso;
    
    - rodarFolha: é rodada folha de pagamento filtrando todos os empregados através dos métidos de pagamento escolhido. Isso         acontece todos os dia. Ao rodar folha levamos em consideracao as horas extras, as taxas e serem deduzidas...
    
    - criarNovaAgenda: quando necessario;
   
   ##### Motivação 
   Usei essa classe para separar as funcionalidades.
   Ela tem um método incomum obter a instância dela mesma através do padrao "Singleton" que permite fazer uma única instância;  
   Nessa classe, temos todos os métodos a ser gerenciado pela AppUso.  
   
   
 
   
## Classe Pessoa:  
   Atributos;  
   - nome;  
   - id;  
   - endereco;  
   - tipo;  
   - salario;  
   ##### Motivação 
   Para agrupar tudo que as subclasses têm em comum.  
   
   ##### Vantagem  
   É que ela permite-nos usar polimorfismo com mais facilidade.  
   
### Herança Classe:  
   #### Comissionado; 
   ##### Motivação:  
   Permite que as informações do tipo de funcionário comissionado seja manipulada unicamente para esta classe.  
     
   ##### Solução  
   Soluciona problema de agrupamento dos métodos específicos na superclasse, pois cada tipo tem algumas coisas de vem ser feita do jeito unico.
   
   ##### Vantagem  
   Melhor organização do código;
   
   #### Asslariado;  
   ##### Motivação:  
   Permite que as informações do tipo de funcionário assalariado seja manipulada unicamente para esta classe.  
     
   ##### Solução  
   Soluciona problema de agrupamento dos métodos específicos na superclasse, sendo que alguns métodos são incomum.
   
   ##### Vantagem  
   Melhor organização do código;    
   
   
   #### Horista; 
   ##### Motivação:  
   Permite que as informações do tipo de funcionário horista seja manipulada unicamente para esta classe.  
     
   ##### Solução  
   Soluciona problema de agrupamento dos métodos específicos na superclasse. Dependendo da particularidade desse funcionário, precisamos implementar alguns métodos particular. Ex: taxa deduzido no salário.
   
   ##### Vantagem  
   Melhor organização do código;
   
   
   #### Gerente: ele é a única pessoa que pode acessar o sistema atravez do usuario e senha;  
   atributos a mais:  
   - usuario;  
   - senha;  
   ##### Motivação  
   Essa classe é para ter único tipo que pode acessar o sistema através de login. As informações não devem ficar aberto a todos;
   
   ##### Vantagem  
   Permite-nos ter mais controle do que será feita no sistema.
                    
## Classe Endereço: 
   ##### Motivação  
   Para deixar a classe pessoa mais reduzido em termos de atributos;
   
   ##### Solução
   Soluciona problema de espalhamento dos atributos relacionados, sendo que podem ser uma coisa só. 
   
   ##### Vantegem  
   Deixa código mais legível;
    Atributos 
   - rua;  
   - cep;  
   - nCasa;  
           
* A partir daqui implementei o padrão Abstract Factory para criar classes sem especificar a classe concreta;            
## Classe CriaFuncionario: 
responsavel pelo assinatura dos método:  
      - criarFuncionario;  
   ##### Motivação
   Essa classe permite-nos instânciar uma classe sem especificar a classe concreta que queremos. Isso feita através do      "Abstract Factory". Ele tem somente a assinatura do método.
   
   ##### Vantagem
   Permite-nos trabalhar com mais cuidado sendo que vamos usar a interface diretamente, evitando mexer na classe concreta.
    
     
* Esta classe retorna uma classe criada atravez de Abstract Factory  
## Classe CriaFuncionarioNormal  
    que herda CriaFuncionario e implementa o metodo:  
      - criarFuncionario e returna um tipo Pessoa;  
   ##### Motivação
   Justamente para aplicação do padrão "Abstract Factory" que além da fábrica abstrata, tem as fábricas concreta. No caso, este é uma das fábricas concretas que retorna um tipo pessoa, que pode ser comissionado ou assalariad ou horista, dependo do tipo passado;
   
   ##### Vantagem  
   Melhor organização do código e só funciona quando é requisitado;
    
 * Esta classe herda Classe CriaFuncionario e retorna um tipo pessoa  
## Classe criaGerente:  
      - criarFuncionario e retorna um tipo pessoa;  
   ##### Motivação  
   Para criar um tipo específico de funcionário que é gerente porque o sistema só pode ser manipulado pelo gerente.
   
   ##### Vantagem  
   Aplicação de padrão "Abstract Factory";
   
# Padrões Usados  
* Abstract Factory - para podermos programar para interface em vez de usar diretamente as classes concretas; É usado para criar as classes herdadas da classe pessoa, que através da classe "abstracta CriarFuncionario" que contém a assinatura do método criarFuncionario, que é implementado nas classes: criaGerente e retorna um objeto Gerente; e criarFuncionarioNormal e retorna um objeto que pode ser horista ou assalariado ou comissionado.  

* Singleton - usado para instânciar uma vez só a classe Sistema na classe AppUso.  
