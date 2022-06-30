# Components
```mermaid
graph TB
  linkStyle default fill:#ffffff

  4["<div style='font-weight: bold'>Mainframe Banking System</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Stores all of the core<br />banking information about<br />customers, accounts,<br />transactions, etc.</div>"]
  style 4 fill:#999999,stroke:#6b6b6b,color:#ffffff
  5["<div style='font-weight: bold'>E-mail System</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>The internal Microsoft<br />Exchange e-mail system.</div>"]
  style 5 fill:#999999,stroke:#6b6b6b,color:#ffffff
  18[("<div style='font-weight: bold'>Database</div><div style='font-size: 70%; margin-top: 0px'>[Container: Oracle Database Schema]</div><div style='font-size: 80%; margin-top:10px'>Stores user registration<br />information, hashed<br />authentication credentials,<br />access logs, etc.</div>")]
  style 18 fill:#438dd5,stroke:#2e6295,color:#ffffff
  8["<div style='font-weight: bold'>Single-Page Application</div><div style='font-size: 70%; margin-top: 0px'>[Container: JavaScript and Angular]</div><div style='font-size: 80%; margin-top:10px'>Provides all of the Internet<br />banking functionality to<br />customers via their web<br />browser.</div>"]
  style 8 fill:#438dd5,stroke:#2e6295,color:#ffffff
  9["<div style='font-weight: bold'>Mobile App</div><div style='font-size: 70%; margin-top: 0px'>[Container: Xamarin]</div><div style='font-size: 80%; margin-top:10px'>Provides a limited subset of<br />the Internet banking<br />functionality to customers<br />via their mobile device.</div>"]
  style 9 fill:#438dd5,stroke:#2e6295,color:#ffffff

  subgraph 11 [API Application]
    style 11 fill:#ffffff,stroke:#444444,color:#444444

    12["<div style='font-weight: bold'>Sign In Controller</div><div style='font-size: 70%; margin-top: 0px'>[Component: Spring MVC Rest Controller]</div><div style='font-size: 80%; margin-top:10px'>Allows users to sign in to<br />the Internet Banking System.</div>"]
    style 12 fill:#85bbf0,stroke:#5d82a8,color:#000000
    13["<div style='font-weight: bold'>Accounts Summary Controller</div><div style='font-size: 70%; margin-top: 0px'>[Component: Spring MVC Rest Controller]</div><div style='font-size: 80%; margin-top:10px'>Provides customers with a<br />summary of their bank<br />accounts.</div>"]
    style 13 fill:#85bbf0,stroke:#5d82a8,color:#000000
    14["<div style='font-weight: bold'>Reset Password Controller</div><div style='font-size: 70%; margin-top: 0px'>[Component: Spring MVC Rest Controller]</div><div style='font-size: 80%; margin-top:10px'>Allows users to reset their<br />passwords with a single use<br />URL.</div>"]
    style 14 fill:#85bbf0,stroke:#5d82a8,color:#000000
    15["<div style='font-weight: bold'>Security Component</div><div style='font-size: 70%; margin-top: 0px'>[Component: Spring Bean]</div><div style='font-size: 80%; margin-top:10px'>Provides functionality<br />related to signing in,<br />changing passwords, etc.</div>"]
    style 15 fill:#85bbf0,stroke:#5d82a8,color:#000000
    16["<div style='font-weight: bold'>Mainframe Banking System Facade</div><div style='font-size: 70%; margin-top: 0px'>[Component: Spring Bean]</div><div style='font-size: 80%; margin-top:10px'>A facade onto the mainframe<br />banking system.</div>"]
    style 16 fill:#85bbf0,stroke:#5d82a8,color:#000000
    17["<div style='font-weight: bold'>E-mail Component</div><div style='font-size: 70%; margin-top: 0px'>[Component: Spring Bean]</div><div style='font-size: 80%; margin-top:10px'>Sends e-mails to users.</div>"]
    style 17 fill:#85bbf0,stroke:#5d82a8,color:#000000
  end

  8-. "<div>Makes API calls to</div><div style='font-size: 70%'>[JSON/HTTPS]</div>" .->12
  8-. "<div>Makes API calls to</div><div style='font-size: 70%'>[JSON/HTTPS]</div>" .->13
  8-. "<div>Makes API calls to</div><div style='font-size: 70%'>[JSON/HTTPS]</div>" .->14
  9-. "<div>Makes API calls to</div><div style='font-size: 70%'>[JSON/HTTPS]</div>" .->12
  9-. "<div>Makes API calls to</div><div style='font-size: 70%'>[JSON/HTTPS]</div>" .->13
  9-. "<div>Makes API calls to</div><div style='font-size: 70%'>[JSON/HTTPS]</div>" .->14
  12-. "<div>Uses</div><div style='font-size: 70%'></div>" .->15
  13-. "<div>Uses</div><div style='font-size: 70%'></div>" .->16
  14-. "<div>Uses</div><div style='font-size: 70%'></div>" .->15
  14-. "<div>Uses</div><div style='font-size: 70%'></div>" .->17
  15-. "<div>Reads from and writes to</div><div style='font-size: 70%'>[JDBC]</div>" .->18
  16-. "<div>Makes API calls to</div><div style='font-size: 70%'>[XML/HTTPS]</div>" .->4
  17-. "<div>Sends e-mail using</div><div style='font-size: 70%'></div>" .->5
```
