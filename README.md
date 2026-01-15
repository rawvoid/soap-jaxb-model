# SOAP JAXB Model

[![Build Status](https://github.com/rawvoid/soap-jaxb-model/workflows/test/badge.svg)](https://github.com/rawvoid/soap-jaxb-model/actions)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Maven Central](https://img.shields.io/maven-central/v/io.github.rawvoid/soap-jaxb-model-parent)](https://central.sonatype.com/artifact/io.github.rawvoid/soap-jaxb-model-parent)

A modern Java library providing JAXB-generated model classes for SOAP 1.1 and SOAP 1.2 protocols. This project leverages Jakarta XML Bind API to create type-safe Java representations of SOAP envelopes, faults, and related structures.

## Features

- 🚀 **Modern Java**: Built with Java 21 and Jakarta EE
- 📦 **Multi-Version Support**: Separate modules for SOAP 1.1 and SOAP 1.2
- 🔧 **Lombok Integration**: Uses Lombok for clean, concise data classes
- 🏗️ **Maven-Ready**: Easy integration with Maven-based projects

## Modules

- **soap-v1_1**: JAXB model classes for SOAP 1.1 specification
- **soap-v1_2**: JAXB model classes for SOAP 1.2 specification

## Usage

Add the dependency to your Maven `pom.xml`:

### SOAP 1.2
```xml
<dependency>
    <groupId>io.github.rawvoid</groupId>
    <artifactId>soap-jaxb-model-v1_2</artifactId>
    <version>1.0.0</version>
</dependency>
```

### SOAP 1.1
```xml
<dependency>
    <groupId>io.github.rawvoid</groupId>
    <artifactId>soap-jaxb-model-v1_1</artifactId>
    <version>1.0.0</version>
</dependency>
```

### Example Usage

```java
import io.github.rawvoid.soap.model.v1_2.Envelope;
import io.github.rawvoid.soap.model.v1_2.Body;
import io.github.rawvoid.soap.model.v1_2.Fault;

// Create a SOAP envelope
Envelope envelope = new Envelope()
    .setBody(new Body()
        .setFault(new Fault()
            .setFaultCode("env:Sender")
            .setFaultReason("Invalid message format")));

// Marshal to XML
JAXBContext context = JAXBContext.newInstance(Envelope.class);
Marshaller marshaller = context.createMarshaller();
marshaller.marshal(envelope, System.out);
```

## Building

This project uses Maven for build management. To build all modules:

To create JAR files:

```bash
mvn clean package
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.

## Keywords

SOAP, JAXB, Java, XML, Web Services, Jakarta EE, Maven, Lombok, SOAP 1.1, SOAP 1.2
