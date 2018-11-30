title: rabbitmq install
date: 2017-05-04 14:25:53
tags:
---
title: rabbitmq install
tags:
---

```
wget https://www.rabbitmq.com/releases/rabbitmq-server/v3.6.9/rabbitmq-server-3.6.9-1.el6.noarch.rpm

wget http://packages.erlang-solutions.com/erlang-solutions-1.0-1.noarch.rpm

rpm -Uvh erlang-solutions-1.0-1.noarch.rpm


yum install erlang   -y





```
```
install scoat

wget --no-cache http://www.convirture.com/repos/definitions/rhel/6.x/convirt.repo -O /etc/yum.repos.d/convirt.repo  
yum install socat  

```

```
yum install rabbitmq-server-3.6.9-1.el6.noarch.rpm

service rabbitmq-server start 

service rabbitmq-server stop


rabbitmq-plugins enable rabbitmq_management 

```

```
rabbitmqctl add_user test test
rabbitmqctl set_user_tags test administrator
rabbitmqctl set_permissions -p / test ".*" ".*" ".*"

```



//	
//	final static String queueName = "helloman";
//	
//	
//	@Bean(name="rabbitTemplate")
//	public RabbitTemplate rabbitTemplate(){;
//		RabbitTemplate template = new RabbitTemplate(newConnectionFactory());
////		template.setExchange("hehe");
//		return template;
//	}
//	
//	@Bean
//	public ConnectionFactory newConnectionFactory(){
//		
//		com.rabbitmq.client.ConnectionFactory connectionFactory = new com.rabbitmq.client.ConnectionFactory();
//		connectionFactory.setUsername("test");
//		connectionFactory.setPassword("test");
//		connectionFactory.setPort(5672);
//		connectionFactory.setHost("47.89.54.184");
////		connectionFactory.setHost("192.168.1.53");
//		CachingConnectionFactory factory = new CachingConnectionFactory(connectionFactory);
//		
//		return factory;
//		
//	}
//	
//	
//	@Bean
//	Queue queue() {
//		return QueueBuilder.nonDurable(queueName)
//                .autoDelete()
//                .exclusive()
//                .withArgument("foo", "bar")
//                .build();
//	}
//	
//	
//	@Bean
//	TopicExchange exchange() {
//		TopicExchange topic = 	new TopicExchange("exchange.hello");
//		topic.setDelayed(true);
//	
//		return topic;
////		  return new TopicExchange("my-exchange", false, true);
//	}
//	
//	
////	@Bean
////	public TopicExchange helloExchange() {
////		return new TopicExchange("hello.world.exchange");
////	}
//	
//	
//	@Bean
//	Binding binding() {
//		return BindingBuilder.bind(queue()).to(exchange()).with("test.*");
//	}
//	
//	@Bean
//	SimpleMessageListenerContainer container(ConnectionFactory connectionFactory, MessageListenerAdapter listenerAdapter) {
//		SimpleMessageListenerContainer container = new SimpleMessageListenerContainer();
//		container.setConnectionFactory(connectionFactory);
//		container.setQueueNames(queueName);
//		container.setMessageListener(listenerAdapter);
//		return container;
//	}
//    @Bean
//    MessageReceiver receiver() {
//            return new MessageReceiver();
//    }
//	@Bean
//	MessageListenerAdapter listenerAdapter(MessageReceiver receiver) {
//		return new MessageListenerAdapter(receiver, "receiveMsg");
//	}