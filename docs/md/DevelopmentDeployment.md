# DevelopmentDeployment
```mermaid
graph TB
  linkStyle default fill:#ffffff

  subgraph 50 [Developer Laptop]
    style 50 fill:#ffffff,stroke:#888888,color:#000000

    subgraph 59 [Docker Container - Database Server]
      style 59 fill:#ffffff,stroke:#888888,color:#000000

      subgraph 60 [Database Server]
        style 60 fill:#ffffff,stroke:#888888,color:#000000

        61[("<div style='font-weight: bold'>Database</div><div style='font-size: 70%; margin-top: 0px'>[Container: Oracle Database Schema]</div><div style='font-size: 80%; margin-top:10px'>Stores user registration<br />information, hashed<br />authentication credentials,<br />access logs, etc.</div>")]
        style 61 fill:#438dd5,stroke:#2e6295,color:#ffffff
      end

    end

    subgraph 53 [Docker Container - Web Server]
      style 53 fill:#ffffff,stroke:#888888,color:#000000

      subgraph 54 [Apache Tomcat]
        style 54 fill:#ffffff,stroke:#888888,color:#000000

        57["<div style='font-weight: bold'>API Application</div><div style='font-size: 70%; margin-top: 0px'>[Container: Java and Spring MVC]</div><div style='font-size: 80%; margin-top:10px'>Provides Internet banking<br />functionality via a<br />JSON/HTTPS API.</div>"]
        style 57 fill:#438dd5,stroke:#2e6295,color:#ffffff
        55["<div style='font-weight: bold'>Web Application</div><div style='font-size: 70%; margin-top: 0px'>[Container: Java and Spring MVC]</div><div style='font-size: 80%; margin-top:10px'>Delivers the static content<br />and the Internet banking<br />single page application.</div>"]
        style 55 fill:#438dd5,stroke:#2e6295,color:#ffffff
      end

    end

    subgraph 51 [Web Browser]
      style 51 fill:#ffffff,stroke:#888888,color:#000000

      52["<div style='font-weight: bold'>Single-Page Application</div><div style='font-size: 70%; margin-top: 0px'>[Container: JavaScript and Angular]</div><div style='font-size: 80%; margin-top:10px'>Provides all of the Internet<br />banking functionality to<br />customers via their web<br />browser.</div>"]
      style 52 fill:#438dd5,stroke:#2e6295,color:#ffffff
    end

  end

  subgraph 63 [Big Bank plc]
    style 63 fill:#ffffff,stroke:#888888,color:#000000

    subgraph 64 [bigbank-dev001]
      style 64 fill:#ffffff,stroke:#888888,color:#000000

      65["<div style='font-weight: bold'>Mainframe Banking System</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Stores all of the core<br />banking information about<br />customers, accounts,<br />transactions, etc.</div>"]
      style 65 fill:#999999,stroke:#6b6b6b,color:#ffffff
    end

  end

  55-. "<div>Delivers to the customer's<br />web browser</div><div style='font-size: 70%'></div>" .->52
  52-. "<div>Makes API calls to</div><div style='font-size: 70%'>[JSON/HTTPS]</div>" .->57
  57-. "<div>Reads from and writes to</div><div style='font-size: 70%'>[JDBC]</div>" .->61
  57-. "<div>Makes API calls to</div><div style='font-size: 70%'>[XML/HTTPS]</div>" .->65
```
