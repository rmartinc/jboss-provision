# Provisioning of keycloak SAML layers to wildfly and EAP

Simple project to create a wildfly or EAP distribution using the `wildfly-maven-plugin` or `eap-maven-plugin` respectively. The server is provisioned with the different layers and the keycloak SAML ones. User `admin` is added to manage the web console (same `admin` password).

To create a wildfly server:

```bash
mvn clean package
```

To create the EAP counterpart:

```bash
mvn clean package -Peap
```

The server is provisioned in the default folder `target/server`:

```bash
cd target/server/bin
./standalone.sh -Djboss.socket.binding.port-offset=1
```

After that just deploy the SAML application normally using the console or CLI interface.
