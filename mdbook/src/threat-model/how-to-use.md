# Using the Threat Model

A simplistic and reduced threat model is provided in this guide. The purpose is to enable a tester to determine which all tests are relevant depending of the context and scope of testing. For example, a *Blackbox Assessment* where no credential is available to the tester will not include any tests that require container level access in the cluster till valid credentials are obtained or provided.

Following points must be consider while using a test case provided in this document

* Each test case will be labelled with *attacker position*
* Each test case will be labelled with *trust boundary* that the test affects or breaches
* Tester must consider test cases based on level of access and *attacker position* label
* Tester must consider test cases based on scope of testing and *trust boundary* label

For example, given a test where

* No cluster access is provided

Any test that is labelled as `External Attacker` will be feasible for the tester.
