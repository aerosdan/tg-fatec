# Portfólio de Projetos Integradores FATEC-SJC - Daniel Delgado
 
### **Sobre mim**
 
Meu nome é Daniel Delgado Rocha Santos da Silva, sou formado em Engenharia de Produção pela ETEP Faculdades-SJC e curso Banco de Dados na FATEC-SJC.
Trabalho como desenvolvedor desde 2018 e atualmente trabalho como Desenvolvedor Backend na DMCard, onde sou membro do time que mantém e desenvolve o produto “DMApp” da empresa.
Antes de trabalhar com T.I. tive a oportunidade de atuar em empresas excelentes em outras áreas como PCP, Projetos, Supply Chain e Co-packer, toda essa bagagem me faz diariamente ter uma visão mais além do que apenas programar, e sim buscar da melhor maneira agregar valor ao resolver um problema ou melhorar algo.
 
### **Contato**
* [GIT Hub](https://github.com/aerosdan/)
* [GIT Lab](https://gitlab.com/DNLMR)
* [LinkedIn](https://www.linkedin.com/in/daniel-delgado-274096194/)
* E-mail: daniel.delgado.rocha@gmail.com
 
### **Principais Conhecimentos**
* Python 
* Golang 
* JS 
* API Rest 
* MySQL, Postgre, Oracle, MS SQL 
* Mongo DB 
 
# **PROJETOS DESENVOLVIDOS**
 
# 🐉 Black Mamba (2º Semestre 2019) 🐉
 
Parceiro acadêmico: FATEC 
Aplicação: Web-bot 
Repositório GIT: [Black Mamba](https://github.com/aerosdan/black_mamba)
 
## **Descrição do Projeto**
 
O Black Mamba foi desenvolvido com a intenção de ser uma solução para um público com interesse em investir em ações, porém sem tempo para adquirir conhecimentos mais densos do assunto. Foi desenvolvido inteiramente em Python e para a versão de desenvolvimento fixamos o banco Inter como empresa a ser utilizada. A aplicação tem as seguintes features:
 
* Obter histórico das ações no últimos 12 meses - é feita uma primeira 'carga' dos valores das ações à fim de ter um comparativo, essa carga é salva no banco de dados;
* Web-scraping em 'tempo real' dos valores das ações - a aplicação monitora o valor das ações durante o dia e salvando em um banco de dados próprio;
* Cadastro de Usuário - o usuário se cadastra na aplicação através do Telegram para receber alertas automáticos do web-bot com dicas "venda a ação / compre a ação";
* Análise de Dados + Notificações - O bot processará os dados obtidos das ações no web-scraping e notifica os usuários, por Telegram e e-mail, caso haja uma situação oportuna para venda/compra da ação;  
* Atendimento automatizado - também é possível que o usuário interaja com o bot a fim de obter algumas informações que gostaria, como gráfico com os valores das ações e maior/menor valor da ação no dia;
              
Essa solução ajudaria pessoas inexperientes em investimentos em ações que querem começar a investir, mas devido à complexidade da bolsa de valores é preciso reforçar que o core dessa aplicação foi montar o web-scraping (obtenção dos valores da ação em tempo real) juntamente com um web-bot que é tanto proativo (notificações de oportunidades) como reativo (interações automatizadas). O algoritmo de projeção dos valores da bolsa não foi o foco do projeto, tendo sido aplicada uma regra simplificada para confirmar eventos oportunos de investimento.
 
## **Tecnologias Utilizadas**

**Python** - praticamente todos da equipe já tinham um conhecimento - em diferentes níveis - na linguagem, então optamos por utilizá-la pois com isso conseguimos proporcionar uma boa curva de aprendizagem para todos os integrantes - os que já conheciam poderiam auxiliar os demais à iniciar na linguagem e também poderiam se aprimorar de forma mais acelerada;
 
**MySQL** - banco relacional escolhido tanto pela familiaridade do time quanto pela disponibilização de um banco em cloud de graça;
 
**Lib Selenium** - o pacote Selenium foi usado para automatizar a interação da aplicação com o navegador da web a partir do Python, especificamente para acessar o site onde os dados da ações ficam;
 
**Lib Beautiful Soup** - o pacote Beautiful Soup foi usado para extrair dados de arquivos HTML e XML, sendo possível através dele navegar e pesquisar pelas informações disponibilizadas na origem dos dados que fizemos a coleta de dados.
 
## **Contribuições Pessoais**
 
**Desenvolvimento** - Nesse projeto contribui bastante no tangente à interações do bot com o usuário por e-mail e pelo Telegram.
Foram desenvolvidas rotinas rotinas diferentes para notificações:
* notificações automáticas e proativas - enviadas em momentos dinâmicos e oportunos para investimento;
* interações reativas - executavam apenas sob demanda do usuário;
* relatórios diários - visam informar o cliente do fechamento de um dia.
Essa gama de diferentes formas de interagir com a aplicação agregaram valor à experiência do usuário pois possibilita que cada um personalize e utilize a ferramenta da forma que mais lhe agrada.
 
## **Hard Skills Desenvolvidas**
 
**Conhecimento em Python** - Pude me aprofundar em recursos importantes na linguagem (que usei durante todos os outros projetos e servem de base até hoje no meu dia-a-dia no trabalho):
* Interação com Email - mime types; 
* Interação com Bot Telegram - automatização do bot;   
* Interação com MySQL através do Python - CRUD; 
* Pandas,Selenium, Beautiful Soup - funcionamento das bibliotecas;
 
## **Soft Skills Desenvolvidas**
 
**Trabalho em Equipe** - tivemos várias dinâmicas aplicadas pelos Master que construiu uma equipe mais sinérgica e focada em resultado;
 **"Aprender a aprender"** - tivemos bastante contato com os Masters do 6º semestre que auxiliaram bastante em 'abrir horizontes' e introduzir novos conceitos e conhecimentos.
 
# 🌉 Bridges (1º Semestre 2020) 🌉

Parceiro acadêmico: Necto  
Aplicação: Plataforma para planejamento de tarefas no dia-a-dia (Gráfico GANTT)   
Repositório GIT: [Bridges](https://github.com/aerosdan/bridges)

## **Descrição do Projeto**

O projeto Bridges visa permitir que o usuário cadastre todos os aspectos de seu ambiente de desenvolvimento (pessoas, projetos, tarefas) e por meio de uma interface prática e interativa permitisse que o usuário consiga elaborar e analisar cenários referente ao planejamento de seus projetos e horas disponíveis de desenvolvimento. A aplicação tem as seguintes features:
* Cadastro de Funcionários - permitir o usuário cadastrar Funcionários e carga horária de trabalho de cada um deles; 
* Cadastro de Projetos e Tarefas - permitir cadastrar Projetos (nome do projeto/cliente) e Tarefas do projeto - cada uma com suas respectivas descrições e tempo estimado para conclusão; 
* Fazer relações entre as entidades - atribuir tarefas para um projeto / funcionários para uma tarefa;
* Interface para o usuário - apresentar às entidades acima de forma clara de forma a destacar possíveis GAPs de horas disponíveis x horas utilizadas. 

## **Tecnologias Utilizadas**

**Python** - foi escolhida a linguagem Python pois entendemos que facilitaria a entrega do projeto (que era mais densa que o primeiro); 
 
**MySQL** - banco relacional escolhido tanto pela familiaridade do time quanto pela disponibilização de um banco em cloud de graça;
 
**Django** - o framework possibilitaria termos mais agilidade em desenvolver em conjunto de uma forma simplificada (centralizando front e backend na mesma aplicação com facilidade), além de ser bem consolidado no mercado e ter uma comunidade muito ativa para pesquisarmos dúvidas e materiais de aprendizagem.

## **Contribuições Pessoais**

**Referência técnica DJANGO** - Após a definição de trabalhar com o Framework Django consegui me aprofundar bem em como a ferramenta funciona. De tal forma que mesmo com a equipe dividida em frentes (back/front) e eu não tendo muito conhecimento em front-end, consegui auxiliar todos os membros do time tecnicamente como um techlead.

**Organização Pastas** - A estrutura de pastas do repositório e o entendimento da arquitetura MTV (model, template, view) do Framework foram aplicadas conforme documentação e aprimoradas conforme andamento do projeto.

**Modelagem de dados + Models (django)** - Primeiramente elaborei o modelo relacional junto à criação das tabelas "na mão" (DDL) para demonstração e testes fora da aplicação. Após testes e ajustes com uma versão mais 'definitiva', passei essa camada para dentro do framework, agregando tanto ao time de desenvolvimento (com as facilidades que o ORM do Django traz) quanto para manutenção da base de dados pela dinâmica de migrations.
 
**Templates (django)** - De forma parecida com os models fizemos as views primeiramente em Wireframe: esboçando como ficariam as telas. Para na sequência construirmos fora do framework (em html/css/js) uma versão mais detalhada do front. Finalmente fizemos a conversão do front para o Pyton/Django usando toda a estrutura de herança que o framework permite.
 
**Views (django)** - As views do DJANGO são semelhantes aos Controllers da arquitetura MVC. Aqui estão as regras de negócio da aplicação e é onde determina o que será apresentado no front - destaco para "O QUE", e não "COMO', uma vez que a view está à nível de backend apenas disponibilizando a informação para o Front. Foram desenvolvidas funcionalidades CRUD para todas as entidades e cada uma delas linkadas a um endpoint diferente com seus respectivos forms para interação do usuário.
 
## **Hard Skills Desenvolvidas**
 
**Modelagem de Banco de Dados** - criar, testar e explorar uma modelagem antes de programar foi muito importante nesse projeto. Mesmo assim alguns aspectos do projeto precisaram ser adaptados, estimulando a competência de adaptar e usar ferramentas auxiliares para manutenção do banco (oriunda do próprio Django);

**Framework DJANGO** - este projeto foi introdutório para mim nesse framework, pela posição que estava pude ver o poder da ferramenta e após o projeto me aprofundei ainda mais na questão de backend, tendo certa facilidade neste momento futuro pela base de API Rest e como é feita interação com o frontend obtida nesse projeto;

**Dinâmica de Frontend** - tendo uma preferência pelo back-end desenvolver um pouco no front foi oportuno para mim pois desmistificou diversas dúvidas e questionamentos. Pude observar como a dinâmica de herança nos templates pode imprimir velocidade no desenvolvimento e manutenção do front.
 
## **Soft Skills Desenvolvidas**
 
**Liderança** - pelo entusiasmo que fiquei em aprender o Framework pude muitas vezes 'puxar' o time para fazermos uma entrega melhor e mais aprimorada de forma similar, por estar por dentro do projeto como um todo, exerci a função como 'ponto de apoio' para o time no tangente à dúvidas e contribui de forma geral com ideias boas para o desenvolvimento;

**Trabalho em Equipe** - nessa função central pude aprender que uma call com 4 pessoas engajadas é infinitamente melhor do que apenas uma pessoa ou até duas programando, ao longo do projeto fui aprimorando técnicas para juntar a equipe em momentos importantes para tomar a decisão em conjunto, trazendo mais precisão nas soluções.
 
# ⚔️ Valcode (2º Semestre 2020) ⚔️
Parceiro acadêmico: SPC  
Aplicação: Plataforma de interação de um usuário final (PF) com informações tangente à seu Score  
Repositório GIT: [Valcode](https://github.com/aerosdan/valcode)
 
## **Descrição do Projeto**
 
O Projeto VALCODE tem a intenção de introduzir o usuário - que na maioria dos casos é uma PF - à dinâmica de Score. Apresentando por meio de uma aplicação WEB como está a saúde do seu score assim como os motivos para tal status e  apresentando dicas de como poderia melhorar seu score e até mesmo atuar em outras frentes - como investimentos em ações - caso seu score esteja com uma boa pontuação. O projeto possui as seguintes features:
* Cadastrar Usuários;
* Conceder, estender ou revogar acessos aos próprios dados;
* Calcular Score;
* Cadastrar transações financeiras (contas pagas, à pagar, vencidas, empréstimos, etc.);
* Geração de relatórios;
* Importação / Exportação de dados em/para arquivo;
 
## **Tecnologias Utilizadas**
 
**Java** - linguagem fixada pela FATEC;

**Spring-boot** - o framework possibilitaria termos mais agilidade em desenvolver em conjunto. Além de ser bem consolidado no mercado e ter uma comunidade muito ativa para pesquisarmos dúvidas e materiais de aprendizagem;

**Oracle** - banco de dados fixado pela FATEC.
 
## **Contribuições Pessoais**
 
Neste projeto atuei principalmente na camada de banco de dados e, como SCRUM Master, orquestrando o time para termos boas entregas no desenrolar do projeto.
 
**Base de Dados** - Fiquei responsável pelo database inicial direto no SQL e gerei dados mockados para o restante da equipe utilizar até termos um dataset disponibilizado pelo cliente. Com o andamento do projeto fomos controlando o banco através do Spring-boot (model) e adicionando as funcionalidade de interação nessa camada da aplicação;

**SCRUM Master** - Consegui contribuir bem com ideias para construir o escopo geral do produto final e orquestrar bem o time em questão de delegar funções e auxiliar em casos de problemas.

## **Hard Skills Desenvolvidas**

**Modelagem de Banco de Dados** - criar, testar e explorar a modelagem;
 
**Spring-boot** - pude ser introduzido ao framework e ver semelhanças e diferenças entre outras ferramentas utilizadas previamente.

## **Soft Skills Desenvolvidas**

**Resiliência** - em um cenário onde a FATEC definiu para todos os grupos utilizarem JAVA, à fim de contribuir da melhor forma para o time escolhi funções dentro da equipe para que pudessemos aproveitar melhor a experiências de alguns membros que tinham mais vivência e familiaridade com a linguagem.
 
# 🐟 Nemo (1º Semestre 2021) 🐟
 
Parceiro acadêmico: GSW  
Aplicação: Plataforma para uso de uma empresa para realizar match entre uma vaga de trabalho com requisitos x candidatos  
Repositório GIT: [Nemo](https://github.com/aerosdan/nemo)
 
## **Descrição do Projeto**
 
O Projeto NEMO visa entregar uma aplicação que resolva o problema de "match" entre candidatos e vagas, onde se possa alcançar os melhores candidatos para as vagas apresentadas com seus diversos requisitos.
 
## **Tecnologias Utilizadas**
 
**Java/Springboot** - linguagem/framework escolhida devida à familiaridade dos membros da equipe;
 
**PostgreSQL** - este SGBD foi escolhido por apresentar uma excelente ferramenta para trabalhar com informações geográficas e índices espaciais: o PostGIS.
 
## **Contribuições Pessoais**
 
**Administração do Banco de Dados** - Neste projeto fiquei responsável pela Administração do Banco de Dados, tendo elaborado o modelo relacional inicial de nossas Bases, realizando adaptações com o desenvolver do projeto. Também desenvolvi de Triggers e Procedures que fazem a seleção de candidatos ao lançar uma vaga com requisitos, trazendo em "tempo real" uma lista de candidatos logo após cadastrar uma vaga.
 
## **Hard Skills Desenvolvidas**
 
**PL/pgSQL** - neste projeto pude explorar opções interessantes de triggers e procedures no Postgre;
 
**PostGIS** - fui introduzido a esta ferramenta e pude me aprofundar ao longo do projeto para auxiliar a busca de candidatos para uma determinada vaga que solicitasse proximidade a empresa.
 
## **Soft Skills Desenvolvidas**
 
**Comunicação** - como praticamente um DBA desenvolvi bem a comunicação com a equipe responsável por desenvolver no SpringBoot, a fim de deixá-los munidos de informações atualizada e precisas, além de estar disponível para auxiliar em eventuais problemas com dados no banco.
 
# 🐠 LMS Nemo (2º Semestre 2021) 🐠
 
Parceiro acadêmico: NESS  
Aplicação: LMS com Chat  
Repositório GIT: [LMS Nemo](https://github.com/aerosdan/nemo-lms)
 
## **Descrição do Projeto**
 
Desenvolver uma solução de dados voltada ao ensino à distância para a gestão e oferta de conhecimento, dando suporte às mais diversas arquiteturas de aprendizagem, alinhado com os objetivos estratégicos a serem alcançados por cada organização que atendemos como clientes. Fazer a gestão de logs para alimentar um Data Warehouse a fim de possibilitar a melhor gestão estratégica do negócio.
 
## **Tecnologias Utilizadas**
 
**Python** - implementação eficaz e simplificada para interação com as bases de dados escolhidas e para tratamento de dados, altamente recomendada e utilizada para essa finalidade;
 
**MongoDB** - base de dados que permite fácil interação e manutenção dos dados;
 
**Rocket Chat** - Sistema de Chat "plug and play" facilmente integrado à nossa solução;
 
## **Contribuições Pessoais**

**ETL** - trabalhamos na ingestão de dados de forma a manter o DW de forma eficiente. Efetuando a extração dos dados do "sistema-fonte", transformando esses dados em um formato que possibilita serem analisados e por fim carregando os dados tratados em uma base de dados (DW).
 
## **Hard Skills Desenvolvidas**
 
**Python** - aplicabilidade da linguagem para interações com MongoDB e transformação de dados;
 
**MongoDB** - interações com o banco NoSQL.
 
## **Soft Skills Desenvolvidas**
 
**Inteligência emocional** - com um ano de pandemia e perto do final do ano o time estava notavelmente esgotado física e psicologicamente, neste projeto foi importante saber lidar em uma situação anti-produtiva para conseguir entregar algo de valor, lidando com diferentes timings de entusiasmos.