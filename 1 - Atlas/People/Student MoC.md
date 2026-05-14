
```meta-bind-button
label: New Student Note
icon: user-pen
style: default
class: ""
cssStyle: ""
backgroundImage: ""
tooltip: ""
id: newPersonButton
hidden: false
actions:
  - type: templaterCreateNote
    templateFile: 5 - Templates/Student Template.md
    folderPath: 1 - Atlas/People
    fileName: New Student
    openNote: true
    openIfAlreadyExists: true
```

# Student MoC

## Templates

- [[Student Template]]

## People

```base
filters:
  or:
    - file.tags.contains("student")
    - file.hasLink(this.file)
properties:
  file.name:
    displayName: Student's Name
views:
  - type: table
    name: My Current Advisees
    filters:
      and:
        - advisor == "Me"
        - currentStudent == true
    sort:
      - property: file.name
        direction: ASC

```
