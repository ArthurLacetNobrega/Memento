# Memento
Apresentação do padrão de projeto Memento

Padrão Memento

Centro Universitário UNIESP

Professora: Drª Alana Morais (alanamm.prof@gmail.com)

Aluno: Arthur Lacet Nóbrega Da Silva Lima (arthurlacet@hotmail.com)


 Memento (Lembrança, Retrato, Snapshot)
	O memento é um padrão de projeto comportamental que permite que você restaure o estado anterior de um objeto sem revelar os detalhes de sua implementação.

Problema
	Há uma necessidade crescente de se armazenar versões dos objetos para que o usuário possa reavê-los quando achar necessário.  Contudo, para acessar o conteúdo do objeto temos alguns problemas, se o objeto estiver público será acessível, porém vulnerável. Ademais, estando ele privado será inacessível. Logo, o problema gira em torno de com acessar o objeto sem comprometer sua integridade.

Solução

	O padrão Memento delega a criação dos retratos do estado para o próprio dono do estado, o objeto originador. Portanto, ao invés de outros objetos tentarem copiar o estado do editor “a partir do lado de fora”, a própria classe do editor pode fazer o retrato já que tem acesso total a seu próprio estado.
O padrão sugere armazenar a cópia do estado de um objeto em um objeto especial chamado memento. Os conteúdos de um memento não são acessíveis para qualquer outro objeto exceto aquele que o produziu. Outros objetos podem se comunicar com mementos usando uma interface limitada que pode permitir a recuperação dos metadados do retrato (data de criação, nome a operação efetuada etc.), mas não ao estado do objeto original contido no retrato.
Tal regra restritiva permite que você armazene mementos dentro de outros objetos, geralmente chamados de cuidadores. Uma vez que o cuidador trabalha com o memento apenas por meio de uma interface limitada, ele não será capaz de mexer com o estado armazenado dentro do memento. Ao mesmo tempo, o originador tem acesso total a todos os campos dentro do memento, permitindo que ele o restaure ao seu estado anterior à vontade.

Consequências

	1. Preservação das fronteiras de encapsulamento. Memento evita a exposição de informação que somente um originador deveria administrar, mas que, contudo, deve ser armazenada fora do originador. O padrão protege outros objetos de aspectos internos potencialmente complexos do Originador, desta maneira preservando as fronteiras de encapsulamento. 
2. Ele simplifica o Originador. Em outros projetos de preservação do encapsulamento, o Originador mantém as versões do estado interno solicitadas pelos clientes. Isso coloca toda a carga de administração do armazenamento sobre o Originador. Deixar os clientes administrarem o estado que solicitam simplifica o Originador e evita que eles tenham que notificar os originadores quando terminarem a utilização. 
3. O uso de mementos pode ser computacionalmente caro. Mementos podem produzir custos adicionais consideráveis se o Originador tiver de copiar grandes quantidades de informação para armazenar no memento, ou se os clientes criam e devolvem mementos para o originador com muita frequência. A menos que seja barato encapsular e restaurar o estado do Originador, o padrão pode não ser apropriado. Veja a discussão sobre incrementabilidade na seção Implementação. 
4. Definição de interfaces mínimas e amplas. Pode ser difícil em algumas linguagens garantir que somente o originador possa acessar o estado do memento. 
5. Custos ocultos na custódia de mementos. Um caretaker é responsável por deletar o memento do qual ele tem a custódia. Contudo, o caretaker não tem ideia do volume ocupado pelo estado do memento. Daí um caretaker leve poder incorrer em grandes custos de armazenamento quando armazena mementos.

