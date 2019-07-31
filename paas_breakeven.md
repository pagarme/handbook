# Conhecendo nosso produto
Muitos dos pontos sobre o nosso produto você deverá já ter aprendido durante o onboarding. Abaixo seguem alguns pontos a mais que achamos importante que você tenha tempo de conhecer.

## API
O principal produto da pagar.me hoje são nossas apis. Nossos maiores clientes e fontes de receita apenas utilizam nossas apis no dia a dia, sem nenhum contato com nossa dashboard. Portanto aprender bem sobre como ela funciona é o primeiro passo para entender como a pagar.me entrega valor para os seus clientes. Recomendo muito que você crie uma coleção no postman com as seguintes requests, porque isso vai te ajudar MUITO no futuro.
Nossas docs estão [aqui](https://docs.pagar.me/docs), [aqui](https://docs.pagar.me/reference) e [aqui](https://pagarme.zendesk.com/hc/pt-br).

- Criando **recebedores**
    - Crie uma conta bancária
    - Crie um recebedor com essa conta bancária
    - Crie um recebedor com uma conta bancária “aberta” na mesma request
    - Atualize os dados de um recebedor
        - Qual o requisito para atualizar conta bancária?
        - Quais os requisitos para atualizar as outras infos?

- Criação de **transação**
    - Cartão de crédito
        - Sem split
        - Com split
        - Sem soft descriptor
        - Com soft_descriptor
        - Sem postback_url
        - Com postback_url (o request bin pode te ajudar muito)
        - Com dados abertos de cartão
        - Com card_hash
        - Veja o resultado dessas transações na sua dashboard de teste
    - Boleto
        - Sem split
        - Com split
        - Variando as datas de validade
        - Com vários soft_descriptors diferentes
        - Com postback_url
    - Estornos
        - Faça estornos completos de cartão e boleto
        - Estornos parciais
        - Estornos parciais com split
        - Qual a diferença do parcial simples pro com split? Por que nossos clientes precisam do estorno parcial com split?
    - Link de pagamento
        - Crie e simule o pagamento em links de pagamento
        - Crie na api
        - Crie na dash pra comparar
        - Como essas transações aparecem na sua dashboard?
    - Saldo
        - Veja o saldo da sua company
        - Agora emita um boleto de valor alto e simule seu pagamento
        - Veja agora o saldo da sua company
        - Veja o saldo dos recebedores
        - Agora emita um boleto de valor alto com split para alguns recebedores específicos e simule seu pagamento
        - Veja agora o saldo dos recebedores
        - Faça um saque pra sua company
        - Faça um saque pra algum recebedor
        - Um recebedor pode sacar seu dinheiro sozinho hoje na pagar.me sem auxílio do lojista? Por quê?
    - Antecipação
        - Veja os limites de antecipação para sua company
        - Veja os limites de antecipação para um recebedor específico
        - Faça uma antecipação para um deles
        - Veja os resultados na dashboard

## Dashs
A pagar.me tem duas dashboards. As dashboards são nossa interface primária com os clientes. É lá que eles gerenciam acessos, recebedores, saldo, saques, antecipações, informações de cadastro, &c. A [dash atual](https://dashboard.pagar.me/), mais antiga, é feita em angular. A [mais nova](https://beta.dashboard.pagar.me/#/account/login), ainda em beta, é feita em react usando um framework open-source muito louco que fizemos, o [former-kit](https://github.com/pagarme/former-kit).

A ideia desse desafio é se familiarizar com as duas dashs e suas várias telas. Coisas que é legal fazer:

- Faça transações
    - Com cartão
    - Com boleto
    - É possível fazer transações com split na dash?
- Veja os dados da sua operação
    - Número de chargebacks
    - Número de transações recusadas
    - Status das transações
- Veja seu extrato
    - Suas transações
    - Dos seus recebedores
    - As taxas envolvidas
    - Quais são as taxas que a pagar.me pode cobrar de um cliente hoje?
- Faça antecipações
    - Para você
    - Para seus recebedores
    - Quais os modelos de antecipações a pagar.me tem?
    - Qual a diferença entre antecipar os recebíveis mais próximos no tempo em relação aos mais afastados? Quais as vantagens e desvantagens de um modelo e outro?

> **Obs.:** nem todas essas funcionalidades já estão disponíveis na nova dashboard! Então se não encontrar, não tem problema.

## Mundo físico
Um dos maiores diferenciais do pagar.me é justamente poder integrar o mundo físico das maquininhas com o online numa mesma solução. Na verdade numa mesma API! Seu desafio aqui é criar um diagrama simples (pode ser umas caixinhas no draw.io) sobre como as seguintes partes se comunicam.
O seals e o stone mais são dois times que podem te ajudar aqui!

* Libabecs
* SDKs
* EMV
* App
* API pagar.me
* Bandeira
* Adquirente
* Emissor

## Aulinhas
Agora que você já molhou seu pezinho na pagar.me, você pode encarar melhor nosso conteúdo central. Nós temos duas reuniões do paas para disseminação de conhecimento. A macarrão à carbonara, que divulga conteúdos técnicos, e a salaa césar, que divulga conteúdos de negócio. Seu líder deve, nesse momento, já ter te adicionado ambas no calendário. [Aqui](https://pagarme.slack.com/archives/CK22GCG79/p1564502275047900) estão os vídeos das edições passadas que gravamos para a posteridade. É muito importante que você assita a algumas delas para aprofundar o que você sabe de pagar.me. Fale com seu líder para que ele te indique as principais que você deve assistir antes de se juntar definitavente ao time.

## Conhecimentos específicos do seu time

## OKRs do seu time
- O que são okrs?
- Quais são os da pagar.me?
- Quais são os do seu time?

## Projeto
_Cada líder define um específico para a pessoa!_

## Dívidas técnicas e de produto que precisamos matar
Nós temos um sem número de [dívidas](https://github.com/pagarme/roadmap/projects/4?fullscreen=true&card_filter_query=label%3A%22d%C3%ADvida+t%C3%A9cnica%22) técnicas e de produto a matar. Os times têm o compromisso de maner algo em torno de 20 a 30% de sua capacidade alocada na resolução dessas dívidas. Pergunte para o seu líder qual o status do seu time e venha nos ajudar!

## Projetos que queremos tirar do papel
### Pirâmide de testes invertida
A [pirâmide de testes](https://github.com/pagarme/roadmap/issues/678) no nosso principal repositório, o `pagarme-core`, é invertida. Temos muitos testes de ponta a ponta e muitos testes intermitentes. Alguns porquee foram mal implementados outros porque dependem do ambiente de sandbox de provedores externos à pagar.me que nem sempre estão de pé.

### Tratamento de erros
O [tratamento de erros](https://github.com/pagarme/roadmap/issues/680) no `pagarme-core` também não segue um padrão claro. Em cada lugar do código, a depender de que ano em que o código foi escrito, faz-se o tratamento de uma forma diferente. Precisamos padronizar essa parte tão importante de qualquer aplicação e disseminar esse padrão pela pagar.me toda.

### Tipos estáticos
A base de código do `pagarme-core` é razoavelmente grande. Trabalhar com ela no dia a dia pode ser muito desafiador para quem não tem familiaridade. Por que então não pensar em migrar paulatinamente para [tipos estáticos](https://github.com/pagarme/roadmap/issues/787)?

### Separação do domínio financeiro do transacional
Nosso domínio financeiro está acoplado ao domínio transacional. Precisamos [separar as interfaces](https://github.com/pagarme/roadmap/issues/459) dos dois e fazê-los se comunicar apenas por essas interfaces.