# Mensageria-jms-activemq

 Mensageria é um conceito que define que sistemas distribuídos, possam se comunicar por meio de troca de mensagens (evento), sendo estas mensagens “gerenciadas” por um Message Broker (servidor/módulo de mensagens).”
O modelo do projeto acima foi utilizado para a criação do projeto que simula uma loja virtual, que é um projeto de exemplo para a utilização do ActiveMQ como Message Broker. O JMS é uma API de mensagens (Java Message Service) que permite a comunicação entre sistemas distribuídos.
execute o ActiveMQ como servidor de mensagens seguindo a documentacao https://activemq.apache.org/components/classic/documentation e fazendo uma copia do projeto para o seu diretorio de trabalho.



# O modelo Publish/Subscribe (Pub/Sub)
A troca de mensagens é baseado no conceito de tópicos, no qual as mensagens são publicadas pelo produtor em um tópico e são entregues automaticamente a todos os consumidores que assinaram o tópico para recebimento de mensagens.

Portanto, ao contrário do modelo PTP, este modelo permite que uma mesma mensagem seja entregue a vários consumidores (relação “um para muitos” entre produtor e consumidor).

![](https://arquivo.devmedia.com.br/REVISTAS/java/imagens/125/5/4.png)

# O Modelo Point-to-Point

A troca de mensagens é baseado no conceito de filas, no qual cada mensagem é enviada por um produtor a uma fila específica, onde ela fica até que seja posteriormente entregue a um consumidor ou até que expire.

Este modelo garante que uma mensagem seja entregue a um único destinatário (relação “um para um” entre produtor e consumidor). Portanto, mesmo que a fila tenha mais de um consumidor ativo, apenas um receberá cada mensagem.

![](https://arquivo.devmedia.com.br/REVISTAS/java/imagens/125/5/3.png)

# Middlewares Orientados a Mensagens

Um middleware orientado a mensagens (MOM) pode ser brevemente descrito como uma categoria de software cujo objetivo principal é permitir a troca de mensagens entre aplicações distribuídas de maneira assíncrona, escalável, segura e confiável.

Vantagens e desvantagens de Middlewares Orientados a Mensagem

Os middlewares orientados a mensagem trouxeram diversos benefícios para a comunicação distribuída entre aplicações corporativas, até então não disponíveis em estratégias síncronas como o RPC. Isto, no entanto, não significa que estratégias de mensageria sejam sempre a melhor opção no cenário de comunicação distribuída.

Ao longo dos anos, ambas as estratégias têm se mostrado adequadas, e o que define o sucesso na utilização de cada uma é a correta escolha para cada contexto de solução.

Com base neste dilema, a seguir são apresentados alguns dos benefícios oferecidos pela comunicação a partir de middlewares orientados a mensagem:

- Comunicação assíncrona;
- Garantia de entrega;
- Persistência das mensagens;
- Mecanismos de autenticação e autorização na troca de mensagens;
- Modelo de entrega Point-to-Point ou Publish/Subscribe;
- Comunicação robusta com tolerância a falhas causadas por conexões lentas, instáveis ou não confiáveis;
- Roteamento e transformação de mensagens;
- Suporte a diferentes tipos de protocolos de comunicação, como HTTP/HTTPS, multicast, SSL, TCP/IP e UDP;
- Suporte a diferentes linguagens de programação.

Mesmo com todas estas vantagens, o modelo de troca de mensagens assíncronas pode apresentar algumas desvantagens, dependendo de certos contextos:

- Costuma ser um modelo de desenvolvimento mais complexo;
- Não garante o envio ordenado de mensagens, mas pode garantir a entrega ordenada (a prioridade das mensagens pode influenciar neste comportamento);
- Inadequado para cenários que exigem o modelo síncrono de comunicação (request/response), dada sua inerente característica assíncrona.

![](https://arquivo.devmedia.com.br/REVISTAS/java/imagens/125/5/2.png)

# A API Java Message Service

Durante anos os diferentes fornecedores de soluções de middlewares orientados a mensagem disponibilizaram APIs próprias para acesso a seus produtos, que estiveram disponíveis a algumas das principais linguagens de programação. Como consequência, uma aplicação que necessitasse utilizar diferentes produtos desta categoria precisava lidar com APIs incompatíveis.

![](https://arquivo.devmedia.com.br/REVISTAS/java/imagens/125/5/5.png)

Os produtos compatíveis com a API JMS são chamados de provedores JMS (ou JMS Providers), e atualmente há vários no mercado, como WebSphere MQ (IBM), SonicMQ (Progress Software), FioranoMQ (Fiorano), ActiveMQ (Apache), HornetQ (JBoss), Oracle AQ (Oracle), EMS (TIBCO), OpenJMS (OpenJMS Group) e RabbitMQ (SpringSource), para citar alguns.

![](https://arquivo.devmedia.com.br/REVISTAS/java/imagens/125/5/6.png)

segue link da referência:
https://www.devmedia.com.br/jms-api-como-desenvolver-sistemas-baseados-em-mensageria/30073