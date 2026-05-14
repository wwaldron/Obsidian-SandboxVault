
```meta-bind-button
label: New Person Note
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
    templateFile: 5 - Templates/Person Template.md
    folderPath: 1 - Atlas/People
    fileName: New Person
    openNote: true
    openIfAlreadyExists: true
```

# People MOC

People Notes are about jotting down notable information about people and linking people back to [Meetings MoC](Meetings%20MoC), etc.

## Templates

- [Person Template](Person%20Template)

## People

```base
filters:
  and:
    - file.hasLink(this.file)
properties:
  file.name:
    displayName: Person
  note.birthday:
    displayName: Birthday
  note.organization:
    displayName: Organization
  note.first-name:
    displayName: First Name
  note.middle-name:
    displayName: Middle Name
  note.last-name:
    displayName: Last Name
views:
  - type: table
    name: People I've Met
    filters:
      and:
        - personMet == true
    order:
      - file.name
      - birthday
      - organization
    sort:
      - property: last-name
        direction: ASC
      - property: first-name
        direction: ASC
  - type: table
    name: People Not Met
    filters:
      and:
        - personMet == false
    order:
      - file.name
      - organization
    sort:
      - property: last-name
        direction: ASC
      - property: first-name
        direction: ASC
    columnSize:
      file.name: 153

```