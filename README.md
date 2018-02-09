CFAKEMAIL
=========

This is a Milter that performs a series of checkings (SPF, header analysis, etc.) when an email arrives at the MTA to determine if it is a legitimate mail or a fake.

To get information about what a Milter is and its differences with a Content Filter see https://en.wikipedia.org/wiki/Milter

Throughout the SMTP dialogue between the MTAs that deliver the mail and the MTA that receives it, the milter adds custom headers (marks) to the mail according to the results of the checks. In order to classify it and take subsequent actions.

The maximum performance, being an MTA exposed to the Internet, was a requirement of this project. For that reason, and to the absence of libraries for Milter with sufficient maturity in other higher level languages ​​at that time (such as Perl), the Milter was developed in C.

The Milter does not delegate to the Resolver of the host to perform DNS querys but has its own implementation of the Resolver to free itself from the impositions of the Resolver of the Host in the Sendmail line and unlike Postfix.
