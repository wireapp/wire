# Security Policy

To report a vulnerability see contact details [below](#reporting-a-vulnerability).

## Security incident policy
Security bug reports are treated with special attention and are handled differently from normal bugs.
In particular, security sensitive bugs are not handled on public issue trackers on GitHub or other company-wide accessible tools but in a private bug tracker.
Information about the bug and access to it is restricted to people in the security bug group, the individual engineers that work on fixing it, and any other person who needs to be involved for organisational reasons.
The process is handled by the security team, which decides on the people involved in order to fix the issue.
It is also guaranteed that the person reporting the issue has visibility into the process of fixing it.
Any security issue gets prioritized according to its security rating.
The issue is opened up to the public in coordination with the release schedule and the reporter.
Security fixes are mentioned in the release notes in a separate section called "Security Fixes" and link to the according advisory and/or issue.
The issue might not be public at the time of the release, depending on the agreed embargo time, but fully documents the issue and any fixes.

## Tracking security issues
Security issues are tracked on an internal vulnerabilities project that can only be accessed by a small number of people.
Once a security issue is triaged and the appropriate code repository is identified, a draft security advisory is created on the corresponding GitHub repository.
This gives the corresponding team access to the vulnerability and allows to involve all people necessary to fix the issue.
Once the issue has been fixed and the embargo ends the advisory is published to the GitHub advisory database.

## Post mortems
Any security issues must be followed by a post mortem to analyze the cause and resolution for the incident.
This template should be used for that purpose.
The document is then stored alongside the vulnerability for future reference.

### Vulnerability Approval Process
While working on security issues, it is important that we don’t disclose the issue to a wider audience prematurely.
It is therefore necessary that any commit related to security fixes should not obviously be identifiable as such.
Therefore tests pointing to the issue might be landed later, commit messages should be obscured, and comments and code should not refer to the issue in any obvious way.
Any security fix must be approved by the security team before it can be merged.
This ensures that the principles above are followed.

## Internal escalation path
When a security issue is identified and entered in the vulnerability tracker it first gets assessed by the security team.
After the assessment, the team leads responsible for the component where the vulnerability lies and the engineering VPs get involved.
Depending on the security rating, the CTO and CEO may get informed as well.
If the vulnerability is relevant to data protection laws, the data protection officer is also informed.

## Disclosure Policy
Everyone involved in the handling of a security issue – including the reporter – is expected to adhere to the following policy.
Any information related to a security issue must be treated as confidential and only shared with trusted partners if necessary, for example to coordinate a release or manage exposure of clients to the issue.
No information must be disclosed to the public before the embargo ends. The embargo time is agreed upon by all involved parties.
It should be as short as possible without putting any users at risk.

## Supported Versions
Only the most recent version of each application is supported.

While there’s currently no bug bounty program we appreciate every report (see [contact details](#reporting-a-vulnerability) below).

## Reporting a Vulnerability
Every vulnerability report will be assessed within 24 hours of receiving it.
If the outcome of the assessment is that the report describes a security issue, the report will be transferred into an issue on the internal vulnerability project for further processing.
The reporter is updated on each step of the process.
We commit to fixing any security issue that we rate MODERATE or higher within 90 days.

* Contact: [vulnerability-report@wire.com](mailto:vulnerability-report@wire.com)
* Encryption: [PGP Key](#pgp-key)

## PGP Key
```
-----BEGIN PGP PUBLIC KEY BLOCK-----

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
mD++rS3VQR9K
=sQT+
-----END PGP PUBLIC KEY BLOCK-----
```

## Security Ratings
Every vulnerability is rated with one of the following four security levels:
* critical
* high
* moderate
* low

security issues include but are not limited to:
* Remote code execution
* (Reflected) XSS
* CSRF
* TLS failure
* Authentication issues
* Memory corruption

### Critical security issues
Any critical security issue requires an immediate fix and subsequent point release.
An issue is critical if it is technically a high security issue that is known to be currently exploited or would put a high number of users at severe risk if being exploited.

### High security issues
An issue is marked as high if it is exploitable and would lead to compromise of user data.

### Moderate security issues
These issues are generally not as severe as high security issues because they require user interaction or require other additional circumstances/vulnerabilities to be exploitable.

### Low security issues
These issues have security implications but don’t have any (known) exploit path (or the exploit requires excessive resources, or is very limited in scope, or leaks insensitive information).

