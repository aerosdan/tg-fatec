# Portfólio de Projetos Integradores FATEC-SJC - Daniel Delgado

# About me

Meu nome é Daniel Delgado Rocha Santos da Silva, sou formado em Engenharia de Produção pela ETEP Faculdades-SJC e curso Banco de Dados na FATEC-SJC. Passei por empresas excelentes durante minha carreria atuando fortemente na área de PCP, Projetos, Supply Chain e Co-packer, passando por empresas como WOW Nutrition e Nestlé tendo atuado nos ultimos anos diretamente com Desenvolvimento e Tecnologia.
Sempre tive contato com técnologia tendo em praticamente todos as empresas trabalhado com 'pensamento digital', em meados de 2018 tive um contato mais direto com programação de fato (PHP) e instantanemanete me apaixonei pela área. Em 2019 comecei a trabalhar como Desenevolvedor na EBI onde pude evoluir muito profissionalmente. Atualmente trabalho como Desenvolvedor Python na DM Card.  
Me considero sortudo na vida pois sempre tive em minha volta pessoas incriveis ao meu redor, tanto em minha vida pessoal - pai, mãe e esposa sensacionais - quanto no profissional - trabalhei com verdadeiras "feras" que me ensinaram muito - e sempre bem suportado no meio acadêmicos pelo docente das instituições - Bissoli e Fortes na ETEP e Sakaue, Sabha e Walmir na FATEC.  

### How to reach me
* [GIT Hub](https://github.com/aerosdan/)
* [GIT Lab](https://gitlab.com/DNLMR)
* [LinkedIn](https://www.linkedin.com/in/daniel-delgado-274096194/)

### Meus Principais Conhecimentos
* Python  
* Golang  
* JS  
* API Rest  
* MySQL, Postgre, Oracle, MS SQL  
* Mongo DB  

# **PROJETOS DESENVOLVIDOS**

# Black Mamba (2º Semetre 2019)

Cliente: FATEC  
Aplicação: Web-bot  
Repositório GIT: [Black Mamba](https://github.com/aerosdan/black_mamba)

## Descrição do Projeto

O Black Mamba foi desenvolvido com a intenção de ser uma solução para um público com interesse de investir em ações, porém sem tempo para adquirir conhecimentos mais densos do assunto. Foi desenvolvido interamente em Python e para a versão de desenvolvimento fixamos o banco Inter como empresa a ser utilizada. A aplicação tem as seguintes features:

* Obter histórico das ações no ultimos 12 meses - é feita uma primeira 'carga' dos valores das ações à fim de ter um comparativo, essa carga é salva no banco de dados;
* Web-scraping em 'tempo real' dos valores das ações - a aplicação monitora o valor das ações durante o dia e salvando em um banco de dados próprio;
* Cadastro de Usuário - o usuário se cadastra na aplicação através do Telegram para receber alertas automaticos do web-bot com dicas "venda a ação / compre a ação";
* Analise de Dados + Notificações - O bot processará os dados obtidos das ações no web-scraping e notifica os usuarios, por telegram e e-mail, caso haja uma situação oportuna para venda/compra da ação;	
* Atendimento automatizado - também é possivel que o usuario interaja com o bot a fim de obter algumas informações que gostaria, como grafico com os valores das ações e maior/menor valor da ação no dia;
				
Essa solução ajudaria pessoas inexperientes em investimentos em ações que querem começar a investir, mas devido à complexidade da bolsa de valores é preciso reforçar que o core dessa aplicação foi montar o web-scraping (obtenção dos valores da ação em tempo real) juntamente com um web-bot que é tanto proativo (notificações de oportunidades) como reativo (interações automatizadas). O algoritmo de projeção dos valores da bolsa não foi o foco do projeto, tendo sido aplicada uma regra simplificada para confirmar eventos oportunos de investimento.

## Tecnologias Utilizadas 

Python - foi escolhida a linguagem Python por ser simplificada para o nosso objetivo e por ter uma curva de aprendizagem mais amigavel - uma vez que estavamos no primeiro semestre na época essa escolha foi a mais sensata;  
MySQL - banco relacional escolhido tanto pela familiaridade do time quanto pela disponibilização de um banco em cloud de graça;
Lib Selenium - o pacote Selenium foi usado para automatizar a interação da aplicação com o navegador da web a partir do Python, especificamente para acessar o site onde os dados da ações ficam;
Lib Beautiful Soup - o pacote Beautiful Soup foi usado para extrair dados de arquivos HTML e XML, sendo possivel através dele navegar, pesquisar pelas informações disponbilizadas na origem dos dados que fizemos a coleta de dados.

## Contribuições Pessoais

Nesse projeto contribui bastante no tangente à interações do bot com o usário por e-mail e pelo Telegram. 

Foram desenvolvidas algumas rotinas para *notificações automaticas e proativas*, que são enviadas em momentos dinamicos e oportunos para investimento, rotinas de *interações reativas*, ou seja executavam apenas sob demanda do usuário assim como *relatórios diarios* que visam informar o cliente do fechamento de um dia.

**Notificações**  

E-mail simples
``` python
def send_text_email(assunto, mensagem, to_addrs):
# Autenticação de Email - host e port padrão do GMAIL
    smtp_ssl_host = 'smtp.gmail.com'
    smtp_ssl_port = 465
    username = 'blackmambabot1@gmail.com'
    password = '' # hidden

    # Definição das váriavéis do envio de Email
    from_addr = 'blackmambabot1@gmail.com'
    message = email.mime.text.MIMEText(mensagem)
    message['subject'] = assunto
    message['from'] = from_addr
    message['bcc'] = to_addrs

    # Realiza conexão segura com o servidor do Email
    server = smtplib.SMTP_SSL(smtp_ssl_host, smtp_ssl_port) 

    # Interação com o servidor: Insere Usuario e Senha
    server.login(username, password) 

    # Interação com o servidor: Envia o Email
    server.sendmail(from_addr, to_addrs, message.as_string()) 

    # Fecha conexão com o servidor do Email
    server.quit() 

    print("E-mail enviado com sucesso!")
```

E-mail com anexo (grafico das ações diario)
```python
def send_attachment_email(assunto, mensagem, to_addrs):
    # Autenticação de Email - host e port padrão do GMAIL
    smtp_ssl_host = 'smtp.gmail.com'
    smtp_ssl_port = 465
    username = 'blackmambabot1@gmail.com'
    password = '' # hidden


    # Definição das váriavéis do envio de Email
    from_addr = 'blackmambabot1@gmail.com'
    message = MIMEMultipart()
    message['subject'] = "IMAGEM BLACKMAMBA - COMPRA A AÇÃO LOGO CARA TA ESPERANDO OQUE"
    message['from'] = from_addr
    message['bcc'] = to_addrs

    # Definição das váriavéis do envio do Anexo
    filename='diario.png'
    attachment  =open(filename,'rb')
    part = MIMEBase('application','octet-stream')
    part.set_payload((attachment).read())
    encoders.encode_base64(part)
    part.add_header('Content-Disposition',"attachment; filename= "+filename)
    message.attach(part)

    # Realiza conexão segura com o servidor do Email
    server = smtplib.SMTP_SSL(smtp_ssl_host, smtp_ssl_port)

    # Interação com o servidor: Insere Usuario e Senha
    server.login(username, password) 

    # Interação com o servidor: Envia o Email
    server.sendmail(from_addr, to_addrs, message.as_string()) 

    # Fecha conexão com o servidor do Email
    server.quit() 

    print("E-mail enviado com sucesso!")

```
**Interações**

Funções basicas do Bot quando ativo
```python
import telepot
from src.db.mysql_connection import connection,cursor
from src.charts.generate_charts import relat_diario, relat_historico
bm= telepot.Bot('822361090:AAEyKBqmmyytRa5BqmpbfGm-ord7yc9v9UY')
def recebeMSG(msg):
    chat_id=msg['chat']['id']
    mens=msg['text'].upper()

    if(mens.__contains__('/START')):
        bm.sendMessage(chat_id, 'Ola, para te ajudar preparamos um menu:')
        bm.sendMessage(chat_id, '/cadastro \n/diario \n/historico ')

    if(mens.__contains__('/CADASTRO')):
        bm.sendMessage(chat_id, "Para se cadastrar, preciso que informe seu email")

    if (msg['text'].__contains__('@')):
        email=msg['text'].upper()
        chat_id=(msg['chat']['id'])
        nome=msg['chat']['first_name'].upper()
        try:
            cursor.execute("INSERT INTO bvzfdagnfqepipz70gyw.Clientes(nome, email, id_chat,gold) VALUES('%s', '%s', %d,NULL)"%(nome , email , chat_id))
            connection.commit()
            bm.sendMessage(chat_id,"Usuario cadastrado com sucesso")
        except:
            bm.sendMessage(chat_id,"Usuario ja possui cadastro")

    if(mens.__contains__('/DIARIO')):
        relat_diario()
        bm.sendMessage(chat_id,"Fique por dentro da movimentacao! ")
        bm.sendPhoto(chat_id,photo=open('../../charts/diario.png', 'rb'))

    if (mens.__contains__('/HISTORICO')):
        relat_historico()
        bm.sendMessage(chat_id, "Fique por dentro da movimentacao! ")
        bm.sendPhoto(chat_id, photo=open('../../charts/historico.png', 'rb'))

bm.message_loop(recebeMSG)
while True:
    pass
```

**Relatórios**

Relatório de fechamento do dia
```python
import telegram
from src.db.mysql_connection import cursor
from src.charts.generate_charts import relat_diario
'''Para o funcionamento será necessario acionar o bot userinfobot no telegram do usuario para ter acesso ao CHAT_ID'''
id_colect=[]
id_chat=[]
x=0
try:
    cursor.execute("select id_chat from bvzfdagnfqepipz70gyw.Clientes")
    id_colect=cursor.fetchall()
    for linha in id_colect:
        # transformando o resultado do select em uma lista interavel
        id_chat.append(str(id_colect[x]).replace(',)','').replace('(',''))
        id_chat[x]=int(id_chat[x])
        x=x+1
    print("Todos os IDs foram coletado")
except:
    print("erro")
x=0
relat_diario()
for id in id_chat:
     # cada usuario de telegram tem o seu proprio chat_id
    chat_id=id_chat[x]

    # identificando o bot reponsavel pelo envio da msg
    bot=telegram.Bot(token='822361090:AAEyKBqmmyytRa5BqmpbfGm-ord7yc9v9UY')
    bot.send_message(chat_id=chat_id, text="Segue fechamento do dia das ações do banco Inter!")
    bot.send_photo(chat_id=chat_id,photo=open('../charts/diario.png', 'rb'))
    print("Mensagem enviada com sucesso para o id: ", id_chat[x])
    x=x+1

```

## Hard Skills Desenvolvidas

Interação com Email - mime types;  
Interação com Bot Telegram - automatização do bot;    
Interação com MySQL através do Python - CRUD;  
Pandas,Selenium, Beautiful Soup - funcionamento das bibliotecas;

## Soft Skills Desenvolvidas

Teamwork - tivemos varias dinamicas aplicadas pelos Master que construiu uma equipe mais sinergica e focada em resultado;  
Network - tivemos bastante contato com os Masters do 6º semestre que auxiliaram bastante em 'abrir horizontes'.

# Bridges (1º Semetre 2020)

Cliente: Necto  
Aplicação: Plataforma para planejamento de tarefas no dia-a-dia (Grafico GANTT)  
Repositório GIT: [Bridges](https://github.com/aerosdan/bridges)

## Descrição do Projeto

#TODO

## Tecnologias Utilizadas 

#TODO

## Contribuições Pessoais

#TODO

## Hard Skills Desenvolvidas

#TODO

## Soft Skills Desenvolvidas

#TODO


# Valcode (2º Semetre 2020)

Cliente: SPC  
Aplicação: Plataforma de interação de um usuário final (PF) com informações tangente à seu Score  
Repositório GIT: [Valcode](https://github.com/aerosdan/valcode)

## Descrição do Projeto

#TODO

## Tecnologias Utilizadas 

#TODO

## Contribuições Pessoais

#TODO

## Hard Skills Desenvolvidas

#TODO

## Soft Skills Desenvolvidas

#TODO


# Nemo (1º Semetre 2021)

Cliente: GSW  
Aplicação: Plataforma para uso de uma empresa para realizar match entre uma vaga de trabalho com requisitos x candidatos  
Repositório GIT: [Nemo](https://github.com/aerosdan/nemo)

## Descrição do Projeto

#TODO

## Tecnologias Utilizadas 

#TODO

## Contribuições Pessoais

#TODO

## Hard Skills Desenvolvidas

#TODO

## Soft Skills Desenvolvidas

#TODO

# LMS Nemo (2º Semetre 2021)

Cliente: NESS  
Aplicação: LMS com Chat  
Repositório GIT: [LMS Nemo](https://www.google.com)

## Descrição do Projeto

#TODO

## Tecnologias Utilizadas 

#TODO

## Contribuições Pessoais
  
#TODO

## Hard Skills Desenvolvidas

#TODO

## Soft Skills Desenvolvidas

#TODO