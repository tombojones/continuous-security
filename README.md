# Continuous security in the pipeline
*how security stopped worrying and learned to love the code*

A common challenge for digital projects is information security, a challenge which is typically made up of two core questions:

1) Is what we're building secure?
2) Can I prove it to others?

Okay, so that's very simply put - the reality is that the security challenges in digital projects can be complex and costly. The adoption of **continuous security** as part of the CI/CD pipeline can however go some way to addressing those challenges.

## Continuous security (CS)?

CS is the act of embedding security testing into your CI/CD pipelines like you would smoke or unit testing. Some of it is built on exist CI/CD features that we can adopt as controls, such as the all important pull request/peer review, while others are custom depending on the development languges, environments and tools you're using.

Lets talk about the most important part of CS first, and it's not what it's built with..

* It should add minimal extra time to the pipeline - if shouldn't slow development down
* It needs to minimise false postives and produce limited 'noise' for low risks
* It needs to be easy to interepret

The bottom line is if you make it slow, noisy and hard to understand then people won't adopt it. Think about CS as a product, and developers as the customer.

## What does it look like?

Taking a java project as an example, the CS pipeline could look like:

0) Code is merged into the master/development branch having been peer reviewed (a key control)
1) Static code anaylsis takes place with tools such as *FindBugs, PMD and CheckStyle*. Results can also be pushed to tools like *SonarQube*. Other tools exist (for java and other lanaguages), as do SaaS offerings
2) Some level of virus/malware scanning (the usefulness of which is up for debate)
3) Dependency checking
4) Web application scanning with tools such as *OWASP ZAP and Arachni*.
