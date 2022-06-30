# LiveDeployment
```mermaid
graph TB
  linkStyle default fill:#ffffff

  subgraph 67 [Customer's mobile device]
    style 67 fill:#ffffff,stroke:#888888,color:#000000

    68["<div style='font-weight: bold'>Mobile App</div><div style='font-size: 70%; margin-top: 0px'>[Container: Xamarin]</div><div style='font-size: 80%; margin-top:10px'>Provides a limited subset of<br />the Internet banking<br />functionality to customers<br />via their mobile device.</div>"]
    style 68 fill:#438dd5,stroke:#2e6295,color:#ffffff
  end

  subgraph 69 [Customer's computer]
    style 69 fill:#ffffff,stroke:#888888,color:#000000

    subgraph 70 [Web Browser]
      style 70 fill:#ffffff,stroke:#888888,color:#000000

      71["<div style='font-weight: bold'>Single-Page Application</div><div style='font-size: 70%; margin-top: 0px'>[Container: JavaScript and Angular]</div><div style='font-size: 80%; margin-top:10px'>Provides all of the Internet<br />banking functionality to<br />customers via their web<br />browser.</div>"]
      style 71 fill:#438dd5,stroke:#2e6295,color:#ffffff
    end

  end

  subgraph 72 [Big Bank plc]
    style 72 fill:#ffffff,stroke:#888888,color:#000000

    subgraph 77 [bigbank-api***]
      style 77 fill:#ffffff,stroke:#888888,color:#000000

      subgraph 78 [Apache Tomcat]
        style 78 fill:#ffffff,stroke:#888888,color:#000000

        79["<div style='font-weight: bold'>API Application</div><div style='font-size: 70%; margin-top: 0px'>[Container: Java and Spring MVC]</div><div style='font-size: 80%; margin-top:10px'>Provides Internet banking<br />functionality via a<br />JSON/HTTPS API.</div>"]
        style 79 fill:#438dd5,stroke:#2e6295,color:#ffffff
      end

    end

    subgraph 82 [bigbank-db01]
      style 82 fill:#ffffff,stroke:#888888,color:#000000

      subgraph 83 [Oracle - Primary]
        style 83 fill:#ffffff,stroke:#888888,color:#000000

        84[("<div style='font-weight: bold'>Database</div><div style='font-size: 70%; margin-top: 0px'>[Container: Oracle Database Schema]</div><div style='font-size: 80%; margin-top:10px'>Stores user registration<br />information, hashed<br />authentication credentials,<br />access logs, etc.</div>")]
        style 84 fill:#438dd5,stroke:#2e6295,color:#ffffff
      end

    end

    subgraph 86 [bigbank-db02]
      style 86 fill:#ffffff,stroke:#888888,color:#000000

      subgraph 87 [Oracle - Secondary]
        style 87 fill:#ffffff,stroke:#888888,color:#000000

        88[("<div style='font-weight: bold'>Database</div><div style='font-size: 70%; margin-top: 0px'>[Container: Oracle Database Schema]</div><div style='font-size: 80%; margin-top:10px'>Stores user registration<br />information, hashed<br />authentication credentials,<br />access logs, etc.</div>")]
        style 88 fill:#438dd5,stroke:#2e6295,color:#ffffff
      end

    end

    subgraph 90 [bigbank-prod001]
      style 90 fill:#ffffff,stroke:#888888,color:#000000

      91["<div style='font-weight: bold'>Mainframe Banking System</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Stores all of the core<br />banking information about<br />customers, accounts,<br />transactions, etc.</div>"]
      style 91 fill:#999999,stroke:#6b6b6b,color:#ffffff
    end

    subgraph 73 [bigbank-web***]
      style 73 fill:#ffffff,stroke:#888888,color:#000000

      subgraph 74 [Apache Tomcat]
        style 74 fill:#ffffff,stroke:#888888,color:#000000

        75["<div style='font-weight: bold'>Web Application</div><div style='font-size: 70%; margin-top: 0px'>[Container: Java and Spring MVC]</div><div style='font-size: 80%; margin-top:10px'>Delivers the static content<br />and the Internet banking<br />single page application.</div>"]
        style 75 fill:#438dd5,stroke:#2e6295,color:#ffffff
      end

    end

  end

  75-. "<div>Delivers to the customer's<br />web browser</div><div style='font-size: 70%'></div>" .->71
  68-. "<div>Makes API calls to</div><div style='font-size: 70%'>[JSON/HTTPS]</div>" .->79
  71-. "<div>Makes API calls to</div><div style='font-size: 70%'>[JSON/HTTPS]</div>" .->79
  79-. "<div>Reads from and writes to</div><div style='font-size: 70%'>[JDBC]</div>" .->84
  79-. "<div>Reads from and writes to</div><div style='font-size: 70%'>[JDBC]</div>" .->88
  79-. "<div>Makes API calls to</div><div style='font-size: 70%'>[XML/HTTPS]</div>" .->91
```
