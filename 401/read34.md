# API Deployment 

> # Django Settings Best Practices 

## Managing Django Settings: Issues 

* Different environments 

*Usually, you have several environments: local, dev, ci, qa, staging, production, etc. Each environment can have its own specific settings (for example: DEBUG = True, more verbose logging, additional apps, some mocked data, etc). You need an approach that allows you to keep all these Django setting configurations.* 

* Sensitive data

*each Django project have SECRET_KEY. On top of this there can be DB passwords and tokens for third-party APIs like Amazon or Twitter. This data cannot be stored in VCS.* 

* Sharing settings between team members 

*need a general approach to eliminate human error when working with the settings.*

* Django settings are a Python code 

*be a problem – instead of key-value pairs, settings.py can have a very tricky logic.*

## Setting Configuration: Different Approaches 

### settings_local.py 

**The basic idea of this method is to extend all environment-specific settings in the settings_local.py file, which is ignored by VCS.**

*Example :*

*settings.py file:*

    ALLOWED_HOSTS = ['example.com']
    DEBUG = False
    DATABASES = {
        'default': {
            'ENGINE': 'django.db.backends.postgresql',
            'NAME': 'production_db',
            'USER': 'user',
            'PASSWORD': 'password',
            'HOST': 'db.example.com',
            'PORT': '5432',
            'OPTIONS': {
                'sslmode': 'require'
            }
        }
    }

    ...

    from .settings_local import *

*settings_local.py file:* 

    ALLOWED_HOSTS = ['localhost']
    DEBUG = True
    DATABASES = {
        'default': {
            'ENGINE': 'django.db.backends.postgresql',
            'NAME': 'local_db',
            'HOST': '127.0.0.1',
            'PORT': '5432',
        }
    }

## 12 Factors

***12 Factors is a collection of recommendations on how to build distributed web-apps that will be easy to deploy and scale in the Cloud. It was created by Heroku, a well-known Cloud hosting provider.*** 

*As the name suggests, the collection consists of twelve parts:* 

1. Codebase
2. Dependencies
3. Config
4. Backing services
5. Build, release, run
6. Processes
7. Port binding
8. Concurrency
9. Disposability
10. Dev/prod parity
11. Logs
12. Admin processes

***Each point describes a recommended way to implement a specific aspect of the project. Some of these points are covered by instruments like Django, Python, pip. Some are covered by design patterns or the infrastructure setup.***

## django-environ 

*Technically it’s a merge of:* 

* envparse
* honcho
* dj-database-url
* dj-search-url
* dj-config-url
* django-cache-url 

## Naming Conventions 

***Naming of variables is one of the most complex parts of development. So is naming of settings. We can’t imply on Django or third-party applications, but we can follow these simple rules for our custom (project) settings:*** 

* Give meaningful names to your settings.
* Always use the prefix with the project name for your custom (project) settings.
* Write descriptions for your settings in comments.

## Django Settings: Best practices 

* Keep settings in environment variables.
* Write default values for production configuration (excluding secret keys and tokens).
* Don’t hardcode sensitive settings, and don’t put them in VCS.
* Split settings into groups: Django, third-party, project.
* Follow naming conventions for custom (project) settings.

> # SSH Tutorial 

## What is SSH 

***SSH, or Secure Shell, is a remote administration protocol that allows users to control and modify their remote servers over the Internet.***

***The service was created as a secure replacement for the unencrypted Telnet and uses cryptographic techniques to ensure that all communication to and from the remote server happens in an encrypted manner.***

***It provides a mechanism for authenticating a remote user, transferring inputs from the client to the host, and relaying the output back to the client.***

***Linux or macOS user can SSH into their remote server directly from the terminal window. Windows users can take advantage of SSH clients like Putty.  You can execute shell commands in the same manner as you would if you were physically operating the remote computer.***

![](https://www.hostinger.com/tutorials/wp-content/uploads/sites/2/2017/07/shell-snapshot.jpg)

## Understanding Different Encryption Techniques

***The significant advantage offered by SSH over its predecessors is the use of encryption to ensure secure transfer of information between the host and the client.***

***Host refers to the remote server you are trying to access, while the client is the computer you are using to access the host.***

***There are three different encryption technologies used by SSH:***

1. Symmetrical encryption
2. Asymmetrical encryption
3. Hashing.

## Symmetric Encryption 

***Symmetric encryption is a form of encryption where a secret key is used for both encryption and decryption of a message by both the client and the host. Effectively, any one possessing the key can decrypt the message being transferred.***

***Symmetrical encryption is often called shared key or shared secret encryption. There is usually only one key that is used, or sometimes a pair keys where one key can easily be calculated using the other key.***

***Symmetric keys are used to encrypt the entire communication during a SSH Session. Both the client and the server derive the secret key using an agreed method, and the resultant key is never disclosed to any third party. The process of creating a symmetric key is carried out by a key exchange algorithm.***

![](https://www.hostinger.com/tutorials/wp-content/uploads/sites/2/2017/07/symmetric-encryption-ssh-tutorial.jpg)

### Asymmetric Encryption 

***Unlike symmetrical encryption, asymmetrical encryption uses two separate keys for encryption and decryption. These two keys are known as the public key and the private key. Together, both these keys form a public-private key pair.***

***The public key, as the name suggest is openly distributed and shared with all parties. While it is closely linked with the private key in terms of functionality, the private key cannot be mathematically computed from the public key. The relation between the two keys is highly complex: a message that is encrypted by a machine’s public key, can only be decrypted by the same machine’s private key. This one-way relation means that the public key cannot decrypt its own messages, nor can it decrypt anything encrypted by the private key.***

***The private key must remain private i.e. for the connection to be secured, no third party must ever know it. The strength of the entire connection lies in the fact that the private key is never revealed, as it is the only component capable of decrypting messages that were encrypted using its own public key. Therefore, any party with the capability to decrypt publically signed messages must possess the corresponding private key.***

![](https://www.hostinger.com/tutorials/wp-content/uploads/sites/2/2017/07/asymmetric-encryption.jpg)

### Hashing 

***One-way hashing is another form of cryptography used in Secure Shell Connections. One-way-hash functions differ from the above two forms of encryption in the sense that they are never meant to be decrypted. They generate a unique value of a fixed length for each input that shows no clear trend which can exploited. This makes them practically impossible to reverse.***

![Hashing](https://www.hostinger.com/tutorials/wp-content/uploads/sites/2/2017/07/ssh-tutorial-hash.jpg)

## How Does SSH Work with These Encryption Techniques 

***The way SSH works is by making use of a client-server model to allow for authentication of two remote systems and encryption of the data that passes between them.***

***SSH operates on TCP port 22 by default. The host (server) listens on port 22 for incoming connections. It organizes the secure connection by authenticating the client and opening the correct shell environment if the verification is successful.***

***The client must begin the SSH connection by initiating the TCP handshake with the server, ensuring a secured symmetric connection, verifying whether the identity displayed by the server match previous records, and presenting the required user credentials to authenticate the connection.***

![working](https://www.hostinger.com/tutorials/wp-content/uploads/sites/2/2017/07/ssh-client-and-server.jpg)

### Session Encryption Negotiation 

***When a client tries to connect to the server via TCP, the server presents the encryption protocols and respective versions that it supports. If the client has a similar matching pair of protocol and version, an agreement is reached and the connection is started with the accepted protocol. The server also uses an asymmetric public key which the client can use to verify the authenticity of the host.***

### how the algorithm works at a very basic level: 

1. Both the client and the server agree on a very large prime number, which of course does not have any factor in common. This prime number value is also known as the seed value. 
2. the two parties agree on a common encryption mechanism to generate another set of values by manipulating the seed values in a specific algorithmic manner. 
3. Both the parties independently generate another prime number. This is used as a secret private key for the interaction.
4. This newly generated private key, with the shared number and encryption algorithm, is used to compute a public key which is distributed to the other computer.
5. The parties then use their personal private key, the other machine’s shared public key and the original prime number to create a final shared key.
6. Now that both sides have a shared key, they can symmetrically encrypt the entire SSH session. The same key can be used to encrypt and decrypt messages.

## Authenticating the User 

***most SSH users use a password. The user is asked to enter the username, followed by the password. These credentials securely pass through the symmetrically encrypted tunnel, so there is no chance of them being captured by a third party.***

***Although passwords are encrypted, it is still not recommended to use passwords for secure connections.***
