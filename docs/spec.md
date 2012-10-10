## Ideahub Spec

*Version 0.1*

### Overview

Ideahub is a place where a group of people share, discuss and develop product ideas.

### Example Scenario

- Team member Joe submits a new idea via web
- Team member Zach comments on Joe's idea
- Team Member Rose uploads a pdf doc and links to Joe's original idea ☢
- Team member Tom up-votes and stars this idea ☢☢
- Joe receives these update notifications via email and continue to develop the idea ☢☢
- Zach adds a tag ☢
- Tom creates an event for online brainstorming and everyone responses with confirmation. ☢☢
- Discussions in the brainstorming are converted into comments and attached to the idea ☢☢
- Joe upgrade the status of the idea to `RFI` aka "Ready for Implementation"

### Foundational Elements in Ideahub

#### `Idea`

A plain text or markdown article.

##### Attributes:

- Title
- Time
- Contributor
- Status
- Votes
- Connections

#### `Comment`

A comment is an `idea` with **host**. A comment can be attached to **any** Ideahub Elements.

Extra Attributes:

- commented_on

#### `File` ☢

A file is an external object, which can be linked to other objects.

##### Attributes:

- Type
- URI

#### `Connection` ☢

All elements in Ideahub . Referencing is preferred again copying.

Attributes:

- Type
- xref

#### `Clip` ☢☢

A clip is a random piece of information. Clips are storing in a central repository for stocking, inspiring, and referencing.

- Name
- Type
- Content Meta

Regular clips may be:

- URLs
- Code Snippets
- Short Text
- Small Images Encoding in **Base64**

### Sharing

### Discussing

#### Voting

#### Tagging

### Developing

#### Status

#### Brainstorming

#### External Connections

### Interfaces

- Web
- API ☢
- Console ☢
- GUI ☢
- Email ☢

### Authorization ☢☢

*NOT_IMPLEMENTED*

#### Possible Plug-ins ☢☢☢

##### Brainstorming

##### Clip-it