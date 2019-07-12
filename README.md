# WCF Interview Questions & Answers

> Click :star:if you like the project. Pull Request are highly appreciated. Follow me [@kansiris87](https://twitter.com/kansiris87) for technical updates.

### Table of Contents

| No. | Questions |
|---- | ---------
|1    | [What is Windows Communication Foundation, WCF?](#What is Windows Communication Foundation, WCF??)|
|2 | [What are the components of WCF?](#What are the components of WCF?)|
|3 | [What is the difference between WCF and Web services?](#What is the difference between WCF and Web services?)|
|4 | [What are different binding supported by WCF?](#What are different binding supported by WCF?)|
|5 | [What is duplex contracts in WCF?](#What is duplex contracts in WCF?)|
|6 | [How do we use MSMQ binding in WCF?](#How do we use MSMQ binding in WCF?)|
|1    | [Explain volatile queues and Dead letter queues?](#Explain volatile queues and Dead letter queues?)|
|2 | [What are the various ways of hosting a WCF service?](#What are the various ways of hosting a WCF service?)|
|3 | [Explain transactions in WCF?](#Explain transactions in WCF?)|
|4 | [What are different isolation levels provided in WCF?](#What are different isolation levels provided in WCF?)|
|5 | [What are the advantages of hosting WCF services in IIS?	](#What are the advantages of hosting WCF services in IIS?	)|
|6 | [What are the various programming approaches for WCF?](#What are the various programming approaches for WCF?)|
|1    | [What are WCF Service Endpoints? Explain?](#What are WCF Service Endpoints? Explain?)|
|2 | [What is DataContractSerializer and How its different from XmlSerializer?](#What is DataContractSerializer and How its different from XmlSerializer?)|
|3 | [How we can use MessageContract partially with DataContract for a service operation in WCF?](#How we can use MessageContract partially with DataContract for a service operation in WCF?)|
|4 | [Please explain briefly different Instance Modes in WCF?](#Please explain briefly different Instance Modes in WCF?)|
|5 | [How can you generate proxy class and configuration file for WCF service?](#How can you generate proxy class and configuration file for WCF service?)|
|6 | [Is there any tool provided by Microsoft for editing configutation file?](#Is there any tool provided by Microsoft for editing configutation file?)|
|1    | [How can you test your new WCF service without writing any client application?](#How can you test your new WCF service without writing any client application?)|
|2 | [How can you configure reliability using .config file?](#How can you configure reliability using .config file?)|
|3 | [How can you implement operation overloading in WCF service?](#How can you implement operation overloading in WCF service?)|
|4 | [What is Known Types?](#What is Known Types?)|
|5 | [What is ServiceKnownType?](#What is ServiceKnownType?)|
|6 | [What is MessageContract?](#What is MessageContract?)|
|1    | [How is the service instance created? How can you manage or control WCF service instance creation?](#How is the service instance created? How can you manage or control WCF service instance creation?)|
|2 | [ Can you control when the service instance is recycled?](# Can you control when the service instance is recycled?)|
|3 | [Can you limit how many instances or sessions are created at the application level?](#Can you limit how many instances or sessions are created at the application level?)|
|4 | [What are session modes in WCF ? How can you make a service as sessionful?](#What are session modes in WCF ? How can you make a service as sessionful?)|
|5 | [What is MEP (Message Exception Pattern) in WCF?](#What is MEP (Message Exception Pattern) in WCF?)|
|6 | [What is Restful service?](#What is Restful service?)|
|6 | [Explain the difference between Transport and Message Level Security](#Explain the difference between Transport and Message Level Security)|

###  What is Windows Communication Foundation, WCF?

WCF helps in building applications to communicate with each other. It is a framework that helps in managing distributed computing. WCF has a layered architecture. It is a part of the .Net Framework 3.0 

### What are the components of WCF?

WCF Service is composed of three components:

Service class: It implements the service needed.

Host environment: is an environment that hosts the developed service.

Endpoints: are the connection points for the clients to connect to the service. Clients find the end points through three components like service contract, binding, and address.

### What is the difference between WCF and Web services?

WCF has a variety of distributed programming infrastructures. WCF offers more flexibility and portability. WCF has better security mechanisms as compared to Web services. Transportation is easier in WCF.

### What are different binding supported by WCF?

Different bindings

Built- in bindings and custom bindings. When the built in or system provided bindings are not suited for the requirement, custom bindings can be issued.

The system –Provided bindings are:

1. BasicHttpBinding:- uses HTTP for transport .

2. WSHttpBinding:- Used for non duplex services

3. WSDualHttpBinding:- Used for Duplex services

4. NetTcpBinding:- Used for cross machine communication

5. NetPeerTcpBinding:- Used for multiple machine communication

6. NetMsmqBinding:- queued binding Used for multiple machine communication.

### What is duplex contracts in WCF?

WCF allows duplex messaging pattern. Services can communicate with client through a callback. Duplex messaging in WCF can be done over different transports, like TCP, Named Pipes and even HTTP 

### How do we use MSMQ binding in WCF?

Message queue allows applications running at different times to send and read messages from queues. WCF uses transactional queue to capture messages, delivered and stored. A non transactional queue can be used as well, though it does not guarantee the assurance of messages being transferred. netMsmqBinding defines a queued binding. This can be used for cross machine communication. Properties of netMsmqBinding allow sending and receiving of messages.

### Explain volatile queues and Dead letter queues.

WCF also uses non transactional queues for storing messages. Such queues are volatile in nature. They are stored in memory and not used in transactions. On shutting down the machine, the queue is lost. They don’t guarantee the transfer of messages.
Dead letter queues: - Dead letter queues are used for failed or dead messages. When a message delivery fails, it is stored in a dead letter queue. MSMQ has two types of dead letter queues recording failed messages for transactional systems and non transactional systems.

### What are the various ways of hosting a WCF service?

Ways of hosting WCF Service

1. Self hosting: - The service code is embedded within the application code. An end point for the service is defined and an instance of SeriveHost is created. A method can be written then to call the service.

2. Managed Windows services: - here, some hosting code is written in the application code. It consists of registering the application domain as a windows service.

3. Internet Information Services: - Does not require any hosting code to be written in the application code. IIS host services can only use HTTP transport mechanism. IIS needs to be installed and configured on the server.

4. Windows process activation service:- Does not require any hosting code to be written in the application code. WAS needs to be installed and configured on the server. WCF uses the listener adapter interface to communicate activation requests. Requests are transported over non HTTP protocols.

### Explain transactions in WCF

Transactions in WCF allow several components to concurrently participate in an operation. Transactions are a group of operations that are atomic, consistent, isolated and durable. WCF has features that allow distributed transactions. Application config file can be used for setting transaction timeouts.

### What are different isolation levels provided in WCF?
The different isolation levels:

1. READ UNCOMMITTED: - An uncommitted transaction can be read. This transaction can be rolled back later.

2. READ COMMITTED :- Will not read data of a transaction that has not been committed yet

3. REPEATABLE READ: - Locks placed on all data and another transaction cannot read.

4. SERIALIZABLE:- Does not allow other transactions to insert or update data until the transaction is complete.

### What are the advantages of hosting WCF services in IIS?

Advantages of hosting WCF services in IIS

1. Provides process activation and recycling ability thereby increasing reliability

2. It is a simplified way of deployment and development of hosted services.

3. Hosting WCF services in IIS can take advantage of scalability and density features of ASP.NET

### What are the various programming approaches for WCF?

Programming approaches for WCF

Imperative: - Different programming languages can be sued for implementing service logic

Configuration based:- Config files can be used to accomplish a task and end points along with security settings

Attributes can be used for declaration for behaviors and contracts

### What are WCF Service Endpoints? Explain.

For Windows Communication Foundation services to be consumed, it’s necessary that it must be exposed; Clients need information about service to communicate with it. This is where service endpoints play their role.
A WCF service endpoint has three basic elements i.e. Address, Binding and Contract.

Address: It defines 'WHERE'. Address is the URL that identifies the location of the service.

Binding: It defines 'HOW'. Binding defines how the service can be accessed.

Contract: It defines 'WHAT'. Contract identifies what is exposed by the service.

### What is DataContractSerializer and How its different from XmlSerializer?

Serialization is the process of converting an object instance to a portable and transferable format. So, whenever we are talking about web services, serialization is very important.

Windows Communication Foundation has DataContractSerializer that is new in .NET 3.0 and uses opt-in approach as compared to 

XmlSerializer that uses opt-out. Opt-in means specify whatever we want to serialize while Opt-out means you don’t have to specify each 
and every property to serialize, specify only those you don’t want to serialize. DataContractSerializer is about 10% faster than XmlSerializer but it has almost no control over how the object will be serialized. If we wanted to have more control over how object should be serialized that XmlSerializer is a better choice.

### How we can use MessageContract partially with DataContract for a service operation in WCF?

MessageContract must be used all or none. If we are using MessageContract into an operation signature, then we must use MessageContract as the only parameter type and as the return type of the operation.
### Please explain briefly different Instance Modes in WCF?

WCF will bind an incoming message request to a particular service instance, so the available modes are:

Per Call: instance created for each call, most efficient in term of memory but need to maintain session.

Per Session: Instance created for a complete session of a user. Session is maintained.

Single: Only one instance created for all clients/users and shared among all.Least efficient in terms of memory.

### How can you generate proxy class and configuration file for WCF service ?

WCF provides an utility svcutil.exe which can be used to generate proxy class and configuration file. Eg:SvcUtil http://localhost:8002/MyService/ /out:Proxy.cs /noconfig

### Is there any tool provided by Microsoft for editing configutation file ?

Yes. Microsoft provides an utility 'SvcConfigEditor.exe' that can edit any configuration fil

### How can you test your new WCF service without writing any client application ?

Microsoft provides a tool which can be used to test any WCF service. To use this tool, open visual studio command prompt and execute the command 'wcftestclient.exe'. It will open a window where you can add many WCF services and test. You can also provide values for input parameters of WCF methods.

### How can you configure reliability using .config file ?
<bindings>
<netTcpBinding>
<binding name = ReliableTCP>
 <reliableSession enabled = "true"/>
 </binding>
</netTcpBinding>
</bindings>

### How can you implement operation overloading in WCF service ?

We can implement operation overloading using 'Name' property of OperationContract attribute. For eg:
[ServiceContract]
interface ICalculator
{
 [OperationContract(Name = "AddInt")]
 int Add(int arg1,int arg2);
 [OperationContract(Name = "AddDouble")]
double Add(double arg1,double arg2);
}

### What is Known Types ?

By default, you can not use a subclass of a data contract class instead of its base class. You need to explicitly tell WCF about the subclass using the KnownTypeAttribute.
For eg
[DataContract]
[KnownType(typeof(SubClass))]
class BaseClass
{
...
}

[DataContract]
class SubClass : BaseClass
{
...
}

### What is ServiceKnownType ?

Instead of using the KnownType attribute on the base data contract, you can apply the ServiceKnownType attribute on a specific operation on the service side.Then,             only that operation(across all supporting services) can accept the known subclass.
[OperationContract]
[ServiceKnownType(typeof(SubClass))]
void AddContact(BaseClass baseObject);

### What is MessageContract ?

WCF uses SOAP messages to transfer information from client to server and vice-versa. It converts data contract to SOAP messages. SOAP message contains Envelope, Header and Body. SOAP envelope contains name, namespace, header and body element. SOAP Header contains important information which are related to communication but not directly related to message. SOAP body contains information which is used by the target.

When you use MessageContract then you have control over the SOAP message. However some restrictions are imposed as below:

You can have only one parameter for a service operation if you are using MessageContract.

You can return either void or MessageContract type from service operation. Service operation can not return DataContract type.

Service operation can accept and return only MessageContract type.

Some important points about MessageContract:
You can mention the MessageHeader or MessageBodyMember to be signed or Encrypted using ProtectionLevel property. The order of the body elements are alphabetical by default.But you can control the order, using Order property in the MessageBody attribute.

###  How is the service instance created? How can you manage or control WCF service instance creation ?

Client request can be served by using single service instance for all users, one service instance for one client, or one instance for one client request. You can control this behavior by using the technique called Instance Management in WCF.
There are three instance modes supported by WCF:

Per-Call: Service instance is created for each client request. This Service instance is disposed after response is sent back to client.

Per-Session (default): Service instance is created for each client. Same instance is used to serve all the requests from that client for a session. When a client creates a proxy to particular service, a service instance is created at server for that client only. When session starts, context is created and when it closes, context is terminated. This dedicated service instance will be used to serve all requests from that client for a session. This service instance is disposed when the session ends.

Singleton: All client requests are served by the same single instance. When the service is hosted, it creates a service instance. This service instance is disposed when host shuts down.

### Can you control when the service instance is recycled ?

Yes, we can control when the service instance is recycled using the ReleaseInstanceMode property of the OperationBehavior attribute. You can control the lifespan of your WCF service. You can set the value of ReleaseInstanceMode property as one of the following:

RealeaseInstanceMode.None: No recycling behavior.

RealeaseInstanceMode.BeforeCall: Recycle a service object before an operation is called.

RealeaseInstanceMode.AfterCall: Recycle a service object after an operation is called.

RealeaseInstanceMode.BeforeAndAfterCall: Recycle a service object both before and after an operation is called.

###  Can you limit how many instances or sessions are created at the application level ?

Yes, you can limit how many instances or sessions are created at the application level. For this, you need to configure throttling behavior for the service in its configuration file. Some of these important properties are:
maxConcurrentCalls limits the total number of calls that can currently be in progress across all service instances. The default is 16.
maxConcurrentInstances limits the number of InstanceContext objects that execute at one time across a ServiceHost. The default is Int32.MaxValue.

maxConcurrentSessions limits the number of sessions a ServiceHost object can accept. It is a positive integer that is 10 by default.

### What are session modes in WCF ? How can you make a service as sessionful ?

ServiceContract attribute offers the property SessionMode which is used to specify the session mode. There are three session modes supported by WCF:

Session.Allowed(default): Transport sessions are allowed, but not enforced. Service will behave as a per-session service only if the binding used maintains a transport-level session.

Session.Required: Mandates the use of a transport-level session, but not necessarily an application-level session.

Session.NotAllowed: Disallows the use of a transport-level session, which precludes an application-level session. Regardless of the service configuration, the service will always behave as a per-call service.

[ServiceContract(SessionMode = SessionMode.NotAllowed)]
interface IMyContract
{
...
}

[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerCall)]
class MyService : IMyContract
{
...
}


### What is MEP (Message Exception Pattern) in WCF ?

MEP describes the way in which Client and Server communicates. It describes how client and server would be exchanging messages to each other. 
There are three types of message exchange patterns:

Request- Replay (default): When client makes a request to the WCF service, it waits to get response from service till receiveTimeout expires. If client does not get any response from the service before receiveTimeout expires, TimeoutException is thrown.

One-Way: When client makes a request to the WCF service, it does not wait for reply from the service. Service does not send any response to the sender, even if any error occurs in the communication. It does not support out or ref parameters. It does not return value to an operation.

Duplex/Callback: Client and service can sends messages to each other by using One-way or request-reply messaging. This MEP is supported by only bidirectional-capable bindings like as WS Dual, TCP and IPC bindings.To make a duplex contract, you must also define a callback contract and assign the typeof that callback contract to the CallbackContract property of your service contract’s ServiceContract attribute.

### What is Restful service ?

REST stands for Representational State Transfer.

REST is an architectural style for building distributed applications. It involves building Resource Oriented Architecture (ROA) by definding resources that implement uniform interfaces using standard HTTP verbs (GET, POST, PUT, and DELETE), and that can be located/identified by a Uniform Resource Identifier (URI).

Any Service which follows the REST architecture style is called as RESTful service.

Characteristics of RESTful services:

We can load the server information using web url in the browser

We can access/modify the server resource using Url.

It allows the client, written in different language, to access or modify the resource in the server using URL.

It uses the http protocol for its communication and it is stateless.

It can transfer the data in XML,JSON,RSS,ATOM.

### Explain the difference between Transport and Message Level Security.

In Windows Communication Foundation, we can configure to use security at different levels

A.Transport Level security means providing security at the transport layer itself. When dealing with security at Transport level, we are concerned about integrity, privacy and authentication of message as it travels along the physical wire. It depends on the binding being used that how WCF makes it secure because most of the bindings have built-in security.

B.Message Level Security

For Tranport level security, we actually ensure the transport that is being used should be secured but in message level security, we actually secure the message. We encrypt the message before transporting it.
