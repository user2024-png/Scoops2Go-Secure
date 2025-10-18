# Scoops2Go Security Requirements

| ID | Requirement | Description | Priority |
|----|--------------|--------------|-----------|
| SR1 | Authentication | System must require JWT-based login for all endpoints. | High |
| SR2 | Authorization | Admin and User roles must have separated privileges. | High |
| SR3 | Data Validation | All user input must be validated server-side. | High |
| SR4 | HTTPS | All connections must use HTTPS to prevent data interception. | High |
| SR5 | Logging | All login attempts and errors must be logged. | Medium |
| SR6 | Secure Storage | Passwords must be hashed using SHA256 or stronger algorithm. | High |
| SR7 | Error Handling | API should not leak sensitive data in error messages. | Medium |
| SR8 | Continuous Integration | Security testing pipeline should run automatically. | High |
