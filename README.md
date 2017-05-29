# TRABALHO 01 : Instagram Bot
Trabalho desenvolvido durante a disciplina de BD 2

    O referido projeto poderá ser:
        a) Um novo sistema/projeto 
        b) Uma expansão de sistema/projeto previamente desenvolvido em disciplinas anteriores 
        (ex: Expansão dos módulos do sistema desenvolvidos em BD1 - incremento mínimo de 50% nos 
        requisitos/complexidade)
    
    OBS Importantes: 
        a) Os projetos/sistemas propostos serão validados pelo professor e pela turma
        b) Se possível é interessante que os novos sistemas estejam correlacionados com alguma área 
        previamente estudada pelo aluno
        c) Caso dependa de alguma instituição/parceiro externo, a base de dados e informações pertinentes 
        a esta devem ser obtidas no prazo de até 15 dias apos aprovação da proposta do trabalho 
        (caso contrário, nova proposta deverá ser apresentada a turma implicando logicamente em um prazo 
        mais curto para realização das atividades e conclusão do trabalho)
        
# Sumário

## 1	COMPONENTES<br>
Hugo Nascimento<br>

### 2	INTRODUÇÃO E MOTIVAÇAO<br>
Este documento contém a especificação do projeto do banco de dados do **Instagram BOT** e motivação da escolha realizada. <br>
      
### 3	MINI-MUNDO<br>
Em um mundo no qual é necessário tomar várias decisões em nossas rotinas, é  imprescindível termos sistemas computacionais para nos ajudar a coletar e analisar dados que estão constantemente mudando a forma como agimos diariamente. 

Essas informações permitem que ternhamos uma visão 360 dos negócios e, na era da tecnologia, as redes sociais estão tomando o foco. Como a utilização dessas redes vem aumentando, empresas precisam encontrar formas de chegar até o consumidor final através delas. Uma dessas redes sociais que estão em foco é o Instagram: Ela traz o conceito de perfis de fotos e vídeos, onde cada pessoa pode compartilhar de forma pública ou privada as fotos que ela compartilha.

Com base na necessidade das empresas, idealizamos a criação de um robô capaz de coletar dados e fornecer estatítiscas a respeito das famosas **# - Hashtags** do Instagram. Esse recurso auxilia na identificação e indexação de mídias, tornando viável para os negócios a pesquisa e descoberta de informações preciosas do mercado a ser explorado.

O Instagram BOT tem o objetivo de realizar a coleta de dados diários sobre postagens de usuários com determinado assunto (definidos por hashtag). Por fim, o sistema será capaz de gerar um relatório de análise com os principais indicadores para a tomada de decisão para uma empresa atuante em determina nicho de mercado.
<br>

### 4	RASCUNHOS BÁSICOS DA INTERFACE (MOCKUPS)<br>
![Alt text](https://github.com/hugohcn/Topicos-Trabalho-BD2/blob/master/Instagram%20BOT.png "Instagram BOT")


### 5	MODELO CONCEITUAL<br>
#### 5.1 NOTACAO ENTIDADE RELACIONAMENTO
![Alt text](https://github.com/hugohcn/Topicos-Trabalho-BD2/blob/master/Instagram%20Bot%20Model%20-%20Conceitual.png?raw=true "Modelo Conceitual")
    
    5.2 NOTACAO UML (Caso esteja fazendo a disciplina de Projeto)

#### 5.3 DECISÕES DE PROJETO
    [atributo]: [descrição da decisão]
    
    EXEMPLO:
    a) Campo endereço: em nosso projeto optamos por um campo multivalorado e composto, pois a empresa 
    pode possuir para cada departamento mais de uma localização... 
    b) justifique!

#### 5.3 DESCRIÇÃO DOS DADOS 
    **USUARIOS:** Tabela que armazena as informações relativas aos usuários do sistema.<br>
    ID: campo do tipo inteiro auto incrementável que identifica unicamente um usuário.<br>
    NOME: campo do tipo VARCHAR, que armazena o nome do usuário.<br>
    SENHA: campo do tipo MD5 que armazena a senha de acesso do usuário.<br>
    EMAIL: campo do tipo VARCHAR que armazena o email do usuário.<br>
    CRIADO EM: Campo do tipo TIMESTAMP que armazena o momento exato da criação do usuário no sistema.<br>
    ATUALIZADO EM: Campo do tipo TIMESTAMP que armazena o momento exato da última atualização do registro do usuário no sistema.<br>

    **CONTA INSTAGRAM:** 
    Tabela que armazena as informações de perfil do usuário assim que ele loga no sistema com a sua conta do Instagram.
    ID: campo do tipo inteiro auto incrementável que identifica unicamente um perfil do Instagram no sistema.<br>
    INSTAGRAM USERNAME: campo do tipo VARCHAR, que armazena o nome do perfil do usuário no Instagram.<br>
    INSTAGRAM FULLNAME: campo do tipo VARCHAR, que armazena o nome completo do perfil do usuário no Instagram.<br>
    INSTAGRAM BIO: campo do tipo VARCHAR, que armazena a descrição biográfica do perfil do usuário no Instagram.<br>
    INSTAGRAM WEBSITE: campo do tipo VARCHAR, que armazena o endereço do website do usuário no Instagram.<br>
    INSTAGRAM API TOKEN: campo do tipo VARCHAR, que armazena a chave de acesso da API para consulta aos dados do Instagram.<br>
    INSTAGRAM PROFILE PICTURE: campo do tipo VARCHAR, que armazena a URL da imagems de perfil do usuário no Instagram.<br>
    INSTAGRAM EMAIL CONTATO: campo do tipo VARCHAR, que armazena o endereço de email preferencial do usuário para eventuais contatos.<br>
    CRIADO EM: Campo do tipo TIMESTAMP que armazena o momento exato da criação do perfil do Instagram do usuário no sistema.<br>
    ATUALIZADO EM: Campo do tipo TIMESTAMP que armazena o momento exato da última atualização do perfil do Instagram do           usuário no sistema.<br>
    
    **BOT:**
    Tabela que armazena as informações relativas aos robores que ficarão buscando informaçõe no Instagram.<br>
    ID: campo do tipo inteiro auto incrementável que identifica unicamente um robô do sistema.<br>
    DATA INICIO EXECUCAO: campo do tipo TIMESTAMP que armazena a data/hora de início de execução do robô no sistema.<br>
    NOME: campo do tipo VARCHAR que armazena o nome do robô no sistema.<br>
    DESCRICAO: campo do tipo VARCHAR que armazena a descrição do robô no sistema.<br>
    TEMPO EXECUCAO: campo do tipo inteiro que armazena a quantidade de horas que um robô está em situação igual a executando       no sistema.<br>
    QUANTIDADE PERFIS INSPECIONADOS: campo do tipo inteiro que armazena a quantidade de perfis do Instagram que foram             inspecionados.<br>
    SITUACAO: Campo VARCHAR que armazena a situação do robô. Possíveis situações: (EX) Em Execução | (PD) Parado | (FN)           Finalizado | (FE) Finalizado com Erro
    CRIADO EM: Campo do tipo TIMESTAMP que armazena o momento exato de criação do robô no sistema.<br>
    ATUALIZADO EM: Campo do tipo TIMESTAMP que armazena o momento exato da última atualização do robô no sistema.<br>
    
    **CONFIGURACOES:** Tabela que armazena as configurações de execução dos robores.
    ID: campo do tipo inteiro auto incrementável que identifica unicamente uma configuração de um robô do sistema.<br>
    QUANTIDADE PERFIS PARADA: campo do tipo INTEIRO que armazena a quantidade de perfis a serem inspecionados até o momento de     parada da execução do robô.<br>
    TEMPO CICLO EXECUCAO: Campo do tipo inteiro que armazena a quantidade de minutos que o sistema deve aguardar após cada         execução/busca no Instagram.<br>
    CRIADO EM: Campo do tipo TIMESTAMP que armazena o momento exato de criação da configuração do robô no sistema.<br>
    ATUALIZADO EM: Campo do tipo TIMESTAMP que armazena o momento exato da última atualização da configuração do robô no           sistema.<br>
    
    **HASHTAGSBUSCA:** 
    Tabela que armazena as as hashtags definidas nas configurações de cada robô.
    ID: campo do tipo inteiro auto incrementável que identifica unicamente uma hashtag a ser buscada por um robô.<br>
    HASHTAG: campo do tipo VARCHAR, que armazena a hashtag a ser buscada.<br>
    CRIADO EM: Campo do tipo TIMESTAMP que armazena o momento exato da criação da hashtag para a configuração do robô.<br>
    ATUALIZADO EM: Campo do tipo TIMESTAMP que armazena o momento exato da atualização da hashtag para a configuração do robô.<br>
    
    **INDICES:** 
    Tabela que armazena os indicadores pesquisados pelos robôs para cada hashtag configurada, por dia.<br>
    ID: campo do tipo INTEIRO auto incrementável que identifica unicamente um indicador (para uma hashtag) a ser buscada/processada por um robô.<br>
    HASHTAG: campo do tipo VARCHAR, que armazena a hashtag que fora processada.<br>
    DATA ANALISE: Campo do tipo DATE que armazena a data de processamento das informações buscadas/processadas pelo robô.<br>
    QUANTIDADE LIKES: Campo do tipo INTEIRO que armazena a quantidade de likes totais recebidas por uma hashtag.<br>
    QUANTIDADE IMAGENS: Campo do tipo INTEIRO que armazena a quantidade de imagens totais processadas para uma hashtag.<br>
    QUANTIDADE VIDEOS: Campo do tipo INTEIRO que armazena a quantidade de vídeos totais processados para uma hashtag.<br>
    CRIADO EM: Campo do tipo TIMESTAMP que armazena o momento exato de criação do índice no sistema.<br>
    ATUALIZADO EM: Campo do tipo TIMESTAMP que armazena o momento exato da atualização do índice no sistema.<br>
    
    **INDICES RELACINADOS:** 
    Tabela que armazena os indicadores relacionados com cada índice processado pelo robô.<br>
    ID: campo do tipo INTEIRO auto incrementável que identifica unicamente um indicador relacionado para uma hashtag processada.<br>
    HASHTAG: campo do tipo VARCHAR, que armazena a hashtag que fora relacionada no processamento do robô.<br>
    CRIADO EM: Campo do tipo TIMESTAMP que armazena o momento exato de criação do índice relacionado com a hashtag processada no sistema.<br>
    ATUALIZADO EM: Campo do tipo TIMESTAMP que armazena o momento exato da atualização do índice no sistema.<br>
    
### 6	MODELO LÓGICO<br>
![Alt text](https://github.com/hugohcn/Topicos-Trabalho-BD2/blob/master/Modelo%20Lo%CC%81gico%20-%20Instagram%20Bot.png "Modelo Lógico")<br>

### 7	MODELO FÍSICO<br>

### 8	INSERT APLICADO NAS TABELAS DO BANCO DE DADOS<br>
#### 8.1 DETALHAMENTO DAS INFORMAÇÕES
        Detalhamento sobre as informações e processo de obtenção ou geração dos dados.
        Referenciar todas as fontes referentes a:
        a) obtenção dos dados
        b) obtenção de códigos reutilizados
        c) fontes de estudo para desenvolvimento do projeto
        
#### 8.2 INCLUSÃO DO SCRIPT PARA CRIAÇÃO DE TABELAS E INSERÇÃO DOS DADOS (ARQUIVO ÚNICO COM):
        a) inclusão das instruções para criação das tabelas e estruturas de amazenamento do BD
        b) inclusão das instruções de inserção dos dados nas referidas tabelas
        c) inclusão das instruções para execução de outros procedimentos necessários

### 9	TABELAS E PRINCIPAIS CONSULTAS<br>
#### 9.1	GERACAO DE DADOS (MÍNIMO DE 1,5 MILHÃO DE REGISTROS PARA PRINCIPAL RELAÇAO)<br>
    Data de Entrega: (Data a ser definida)
<br>
OBS: Incluir para os tópicos 9.2 e 9.3 as instruções SQL + imagens (print da tela) mostrando os resultados.<br>

#### 9.2	SELECT DAS TABELAS COM PRIMEIROS 10 REGISTROS INSERIDOS<br> 
    Data de Entrega: (Data a ser definida)
<br>
#### 9.3	SELECT DAS VISÕES COM PRIMEIROS 10 REGISTROS DA VIEW<br>
        a) Descrição da view sobre que grupos de usuários (operacional/estratégico) <br>
        e necessidade ela contempla.
        b) Descrição das permissões de acesso e usuários correlacionados (após definição <br>
        destas características)
    Data de Entrega: (Data a ser definida)
<br>
#### 9.4	LISTA DE CODIGOS DAS FUNÇÕES, ASSERÇOES E TRIGGERS<br>
        Detalhamento sobre funcionalidade de cada código.
        a) Objetivo
        b) Código do objeto (função/trigger/asserção)
        c) exemplo de dados para aplicação
        d) resultados em forma de tabela/imagem
<br>
#### 9.5	Administração do banco de dados<br>
        Descrição detalhada sobre como serão executadas no banco de dados as <br>
        seguintes atividades.
        a) Segurança e autorização de acesso:
        b) Estimativas de aquisição de recursos para armazenamento e processamento da informação
        c) Planejamento de rotinas de manutenção e monitoramento do banco
        d) Plano com frequencia de análises visando otimização de performance
<br>
#### 9.6	Backup do Banco de Dados<br>
        Detalhamento do backup.
        a) Tempo
        b) Tamanho
        c) Teste de restauração (backup)
        d) Tempo para restauração
        e) Teste de restauração (script sql)
        f) Tempo para restauração (script sql)
<br>
Data de Entrega: (Data a ser definida)
<br>
#### 9.7	APLICAÇAO DE ÍNDICES E TESTES DE PERFORMANCE<br>
    a) Lista de índices, tipos de índices com explicação de porque foram implementados
    b) Performance esperada VS Resultados obtidos
    c) Tabela de resultados comparando velocidades antes e depois da aplicação dos índices.
<br>
    Data de Entrega: (Data a ser definida)
<br>   
#### 9.8	ANÁLISE DOS DADOS COM ORANGE<br>    
    a) aplicação de algoritmos e interpretação dos resultados
<br>
    Data de Entrega: (Data a ser definida)
<br>
### 10	ATUALIZAÇÃO DA DOCUMENTAÇÃO/ SLIDES E ENTREGA FINAL<br>
<br>
    Data de Entrega: (Data a ser definida)
<br>
### 11	DIFICULDADES ENCONTRADAS PELO GRUPO<br> 
