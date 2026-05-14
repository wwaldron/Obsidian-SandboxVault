
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
  note.studentLevel:
    displayName: Level
  note.advisor:
    displayName: Advisor
  note.email:
    displayName: Email
views:
  - type: table
    name: My Current Advisees
    filters:
      and:
        - advisor == "Me"
        - currentStudent == true
    order:
      - file.name
      - email
      - studentLevel
    sort:
      - property: last-name
        direction: ASC
    columnSize:
      file.name: 198
      note.email: 150
  - type: table
    name: All My Advisees
    filters:
      and:
        - advisor == "Me"
        - currentStudent == true
    order:
      - file.name
      - email
      - studentLevel
    sort:
      - property: last-name
        direction: ASC
    columnSize:
      file.name: 198
      note.email: 150
  - type: table
    name: All Students
    filters:
      and:
        - currentStudent == true
    order:
      - file.name
      - advisor
      - email
      - studentLevel
    sort:
      - property: last-name
        direction: ASC
    columnSize:
      file.name: 198
      note.advisor: 169
      note.email: 150
      note.studentLevel: 101
  - type: table
    name: Undergraduates
    filters:
      and:
        - currentStudent == true
        - studentLevel == "Undergraduate"
    order:
      - file.name
      - advisor
      - email
      - studentLevel
    sort:
      - property: last-name
        direction: ASC
    columnSize:
      file.name: 198
      note.advisor: 169
      note.email: 150
      note.studentLevel: 101
  - type: table
    name: Masters
    filters:
      and:
        - currentStudent == true
        - studentLevel == "Masters"
    order:
      - file.name
      - advisor
      - email
      - studentLevel
    sort:
      - property: last-name
        direction: ASC
    columnSize:
      file.name: 198
      note.advisor: 169
      note.email: 150
      note.studentLevel: 101
  - type: table
    name: PhD
    filters:
      and:
        - currentStudent == true
        - studentLevel == "PhD"
    order:
      - file.name
      - advisor
      - email
      - studentLevel
    sort:
      - property: last-name
        direction: ASC
    columnSize:
      file.name: 198
      note.advisor: 169
      note.email: 150
      note.studentLevel: 101
  - type: table
    name: Post Docs
    filters:
      and:
        - currentStudent == true
        - studentLevel == "Post Doc"
    order:
      - file.name
      - advisor
      - email
      - studentLevel
    sort:
      - property: last-name
        direction: ASC
    columnSize:
      file.name: 198
      note.advisor: 169
      note.email: 150
      note.studentLevel: 101
  - type: table
    name: Graduated Students
    filters:
      and:
        - currentStudent == false
        - studentLevel == "Graduated"
    order:
      - file.name
      - advisor
      - email
      - studentLevel
    sort:
      - property: last-name
        direction: ASC
    columnSize:
      file.name: 198
      note.advisor: 169
      note.email: 150
      note.studentLevel: 101

```
