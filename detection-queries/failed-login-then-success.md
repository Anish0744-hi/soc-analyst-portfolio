# Detection Rule: Successful Login After Repeated Failures

## Objective
Identify potentially suspicious authentication activity where multiple failed login attempts are followed by a successful login for the same user from the same source IP address.

## Detection Conditions
- At least 3 failed login attempts.
- Same username and source IP address.
- A successful login within 5 minutes of the failed attempts.

## Sample Security Logs

| Time | Username | Source IP | Result |
|---|---|---|---|
| 10:01:05 | alex | 198.51.100.24 | Failed |
| 10:01:15 | alex | 198.51.100.24 | Failed |
| 10:01:25 | alex | 198.51.100.24 | Failed |
| 10:01:35 | alex | 198.51.100.24 | Failed |
| 10:01:45 | alex | 198.51.100.24 | Success |

*These are fictional training events. The IP address belongs to a reserved documentation range.*

## Expected Result
Generate an alert because four failed attempts were followed by a successful login for the same user and source IP within 40 seconds.

## Possible False Positives
- A legitimate user repeatedly entering an incorrect password.
- A user successfully logging in after remembering the correct password.
- Automated systems retrying authentication with outdated credentials.

## Recommended Investigation
1. Check whether the source IP and device are familiar.
2. Review MFA results and authentication history.
3. Examine activity after the successful login.
4. Check for privilege changes or access to sensitive files.
5. Escalate according to the incident response procedure if suspicious evidence is found.

## Analyst Conclusion
The activity is suspicious and warrants investigation. The available events alone do not confirm account compromise.
