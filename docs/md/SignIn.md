# SignIn
```mermaid
graph TB
  linkStyle default fill:#ffffff

  subgraph 11 [API Application]
    style 11 fill:#ffffff,stroke:#444444,color:#444444

    12["<div style='font-weight: bold'>Sign In Controller</div><div style='font-size: 70%; margin-top: 0px'>[Component: Spring MVC Rest Controller]</div><div style='font-size: 80%; margin-top:10px'>Allows users to sign in to<br />the Internet Banking System.</div>"]
    style 12 fill:#85bbf0,stroke:#5d82a8,color:#000000
    15["<div style='font-weight: bold'>Security Component</div><div style='font-size: 70%; margin-top: 0px'>[Component: Spring Bean]</div><div style='font-size: 80%; margin-top:10px'>Provides functionality<br />related to signing in,<br />changing passwords, etc.</div>"]
    style 15 fill:#85bbf0,stroke:#5d82a8,color:#000000
  end

  18[("<div style='font-weight: bold'>Database</div><div style='font-size: 70%; margin-top: 0px'>[Container: Oracle Database Schema]</div><div style='font-size: 80%; margin-top:10px'>Stores user registration<br />information, hashed<br />authentication credentials,<br />access logs, etc.</div>")]
  style 18 fill:#438dd5,stroke:#2e6295,color:#ffffff
  8["<div style='font-weight: bold'>Single-Page Application</div><div style='font-size: 70%; margin-top: 0px'>[Container: JavaScript and Angular]</div><div style='font-size: 80%; margin-top:10px'>Provides all of the Internet<br />banking functionality to<br />customers via their web<br />browser.</div>"]
  style 8 fill:#438dd5,stroke:#2e6295,color:#ffffff

  8-. "<div>1. Submits credentials to</div><div style='font-size: 70%'>[JSON/HTTPS]</div>" .->12
  12-. "<div>2. Validates credentials<br />using</div><div style='font-size: 70%'></div>" .->15
  15-. "<div>3. select * from users where<br />username = ?</div><div style='font-size: 70%'>[JDBC]</div>" .->18
  18-. "<div>4. Returns user data to</div><div style='font-size: 70%'>[JDBC]</div>" .->15
  15-. "<div>5. Returns true if the hashed<br />password matches</div><div style='font-size: 70%'></div>" .->12
  12-. "<div>6. Sends back an<br />authentication token to</div><div style='font-size: 70%'>[JSON/HTTPS]</div>" .->8
```
