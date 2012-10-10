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
- Joe upgrades the status of the idea to `RFI` aka "Ready for Implementation"

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

### Sharing, Discussing and Developing

#### Voting ☢

User can vote an idea to show her/him interest. The default order of listing ideas is by sorting by votes.

#### Tagging ☢

Tag is a basic attribute of all elements in Ideahub. Tags can be added to elements and view of every list of element should support filtering by tags.

#### Brainstorming ☢☢

#### Notifications ☢☢

- Web
- IM
- Email

#### Statistics ☢☢

- Activity
- By Status
- Hot Resources
- Contributions
- Timeline

#### Public Activities ☢☢

Any "CRUD" operation on any elements generates a log record. User profile shows public activities.

#### Status

Status is a property of all ideas. It is used by sorting, organizing and statistics.

Here is an ordered list of common status:

1. Undefined
2. Initial Thought
3. Acknowledged
4. Growing
5. RFI
6. Developing
7. Shipped
 
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

Clip-it is a plug-in for quickly drop pieces of information to repository. Clip-it works as a OS X service or browser add-on, grab selected objects and send them out using API.

##### Inspire-me

This plug-in gathers information base upon existing docs and discussions, automatically generate key words and run a Google search. The search result which contains text, picture and multimedia contents are displayed in a well organized view with slide or fade-in-out effects to inspire users.