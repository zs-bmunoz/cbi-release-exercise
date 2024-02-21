# cbi-release-exercise

The objective of this exercise is to demonstrate the knowledge you have about automation in a release process.

That the final result is a satisfactory pipeline that meets all the requirements is not as important as being able to justify the implementation and technical decisions made and discarded.

## Exercise
Create a CI pipeline to be executed in the continuous integration tool of your choice (Jenkins, Gitlab, and so on) on a fork of the current repository.

- Check the integrity of the changes to be introduced in this repository
- Make available a report of the vulnerabilities that are introduced. Trivy is an option, but not mandatory, feel free to use the tool you consider
- Do not allow introduce changes if new HIGH or Critical Vulnerability are part of the new code
- Notify about vulnerabilities introduced to the stakeholders


## Tip: Trivy

[Trivy](https://trivy.dev/) is an open-source vulnerability scanner for containers. It is not needed to know about the tool to reach this exercise. Some commands that can be useful if you consider.

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






