# cbi-release-exercise

The objective of this exercise is to demonstrate the knowledge you have about automation in a release process.

We will evaluate the exercise in a meeting with you, where you will explain the technical decisions taken, the limitations that you find, and the changes that you need to achieve on the current code to make it more secure. Even you can do something extra if you want to demonstrate specific knowledge.

In that way, we will be able to evaluate your knowledge, attention to detail, and way of thinking, going beyond the result of the exercise.

If you are able to make it running in a CI tool, you should prove during the meeting.


## Exercise

Create a CI pipeline that:

- Check the integrity of the changes to be introduced in this repository (just contains the exercise folder with a Dockerfile)
- Make available a report of the vulnerabilities that are introduced. Trivy is an option, but not mandatory, feel free to use the tool you consider
- Do not allow introduce changes if new HIGH or Critical Vulnerability are part of the new code
- Report new vulnerabilities

### Notes

- Take your fork as the main repository to be able to manage it as an administrator. If you are using other repository management tool, please import this repository there.
- It is essential to justify the decisions made regarding the developed pipeline as well as the tools used to demonstrate its operation.
- Feel free to update the Dockerfile if you consider some changes are needed to improve security detection
- You can rely on continuous integration tools
- The repository that you will work on will be shared with the interviewers at least after the interview
- Execute the pipeline during the interview to demonstrate its functionality and consistency in case you have reached a functional solution


## Tip: Trivy

[Trivy](https://trivy.dev/) is an open-source vulnerability scanner for containers. It is not needed to know about the tool to reach this exercise. Some commands that can be useful if you consider.

In case you decide to use Trivy either because of your preference, because it is free, or because you have never used a similar tool, here are a series of examples that may be of interest to you.

Scan a container image for vulnerabilities:
```
trivy i ubuntu:20.04
```

Scan a container image for vulnerabilities but ignore all vulnerabilities that do not have a fix available:
```
trivy i --ignore-unfixed ubuntu:20.04
```

Scan a container image for vulnerabilities but filter for HIGH and CRITICAL vulnerabilities
```
trivy image --severity HIGH,CRITICAL --vuln-type os postgres:10.6
```

Scan a container image for vulnerabilities saving the output in json format
```
trivy image  postgres:10.6 --format json --output <your_file.json>
```

Scan any GH repository for vulnerabilities:
```
trivy repo --vuln-type library https://github.com/raesene/sycamore
```