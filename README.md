# Prova-2

Classe AppUso:
  tem opcao para gerente fazer login e maneger sistema de acordo com as opcoes disponiveis.
  Aqui fica a funcão main e obtem a instancia do sistema atraves de padrao "Singleton";
  
  
Classe Sistema:
tem um metodo para obter a instancia desse objetco atraves do padrao "Singleton";
  Métodos:
    adicionarEmpregado: adiciona empregado especificando se é gerente;
                        se empregado normal especifica tipo (horista, assalariado, comissionado0);
                        
    removerEmpregado: remover empregado atravez de ID unico;
    
    lancarCartaoPonto: recebe um ID e seta a hora da entra ou saida na ListCartao deste;
    
    lancarResultadoVenda: recebe um ID e adicionado a List de venda e tambem List associado ao empregado;
    
    lancarTaxa: este a associa taxa de servico ao empregado atravez de ID;
    
    alterarDetalhes: recebe o ID e altera os atributos necessariso;
    
    rodarFolha: é rodada folha de pagamento filtrando todos os empregados atravez dos metidos de pagamento escolhido. Isso         acontece todos os dia. Ao rodar folha levamos em consideracao as horas extras, as taxas e serem deduzidas...
    
    
    criarNovaAgenda: quando necessario;
   
   
Classe Pessoa:
    atributos;
    nome;
    id;
    endereco;
    tipo;
    salario;
    
Herança Classe:
      Comissiona;
      Asslariado;
      Horista;
      Gerente://ele é a única pessoa que pode acessar o sistema atravez do usuario e senha;
        atributos a mais:
          usuario;
          senha;
                    
Classe Endereço:
    contem rua;
           cep;
           nCasa;
           
//A partir daqui implementei o padrão Abstract Factory para cria classes sem especificar a classe concreta;          
Classe CriaFuncionario:
    responsavel pelo assinatura dos método:
      +criarFuncionario;
     
   // Esta classe retorna uma classe criada atravez de Abstract Factory
    Classe CriaFuncionarioNormal que herda CriaFuncionario e implementa o metodo:
      criarFuncionario e returna um tipo Pessoa;
    
   //Esta classe herda Classe CriaFuncionario e retorna um tipo pessoa
   classe criaGerente:
      criarFuncionario e retorna um tipo pessoa;
      
