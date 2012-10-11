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
- Origin (for Forking)
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

All elements in Ideahub are connect-able. Referencing is preferred again copying.

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

#### `Milestone (Snapshot)` ☢☢

A relatively stable version of an idea. Kind of like a "snapshot", means this is a new version that we all agree on, archive it here for future reference. Setting a new milestone does not necessarily means changing the `Status`. Group members can got many milestones even when the idea is in the `Initial Thought` phase.

Milestones are very useful while displaying the Timeline, reminding the group members how they actually reach the final idea.

Attributes:

- Timestamp
- All connections and so on

#### `Tombstone` ☢☢

Ideas never die, but they need to be put somewhere. Here is the tombstone. Put a death reason tag on an idea, maybe the reason is the limitation of hardware, or simply bad timing, whatever it is, we need to save it. Some time in the future, maybe the `Ship` of an idea, we can bring these ideas back to life, and have a second thought on that.

Attributes:

- Timestamp
- Death reson


### Sharing, Discussing and Developing

#### Forking ☢☢☢

One of the most import feature in Ideahub is `Forking`. Forking means:

> "I like the idea but I would go along another direction."

Almost everything form the original idea can be "inherited" or "overrode" optionally.

#### Voting ☢

User can vote an idea to show her/him interest. The default order of listing ideas is by sorting by votes.

#### Tagging ☢

Tag is a basic attribute of all elements in Ideahub. Tags can be added to elements and view of every list of element should support filtering by tags.

#### Session ☢

Whenever group members wants to discuss something, they will start a new session(in blahtime of course). During the session, everthing about the idea(the connections, the timeline and so on) will be displayed. After the session finished(normally), the discussion will be attached automatically to the idea through a new connection. However, if the sessions ends abnormally(someone slams the door by click the 'X' button in the browser), the discussion contents will also be saved, but will be tagged as something like 'Not closed yet'.

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

Any "CRUD" operation on any element generates a log record. User profile shows public activities.

#### Status

Status is a property of all ideas. It is used by sorting, organizing and statistics.

Here is an ordered list of common status:

1. `Undefined`
2. `Initial Thought`
3. `Acknowledged`
4. `Growing`
5. `RFI`
6. `Developing`
7. `Shipped`
 
#### External Connections

##### Service Hooks

### Interfaces

- Web
- API ☢
- Console ☢
- GUI ☢
- Email ☢

### Authorization ☢☢

*NOT_IMPLEMENTED*

*@vm*

IdeaHub serves as an open platform in a way that provides data for other services. Some(maybe all) ideas are not free, so anyone who wants to get access to the data must be granted by end users. So ideahub needs to provide a way users can rely for services. We choose OAuth2.

#### OAuth2

Implement / Grap an opensource implementation that conform to OAuth2 protocal.

- OAuth2 service will serve as the core authorization service
- Third-party applications will use a set of fixed URLs to get the permission for resources

#### Possible Plug-ins ☢☢☢

##### Brainstorming

*@long*

##### HUD - Heads Up Display

Isn't it really cool to give a group member a little "heads up", eg, the background, the idea status during the brainstorming?

Things that will be displayed on HUD:

- Idea & it's summary
- Flash cards / Key point list from the previous discussions & comments & connections
- Members in the room & (possibly) their moods, their locations and their everything
- How long the session has taken
- Some predefined key points for this session & how many has already been discussed
- How long can I still get focus on this session? (I can rate my self, and the session holder can see all member's self estimation, in case the session is too long for members to focus)
- What have been settled during the discussion period

##### Clip-it

Clip-it is a plug-in for quickly drop pieces of information to repository. Clip-it works as a OS X service or browser add-on, grab selected objects and send them out using API.

##### Inspire-me

This plug-in gathers information base upon existing docs and discussions, automatically generate key words and run a Google search. The search result which contains text, picture and multimedia contents are displayed in a well organized view with slide or fade-in-out effects to inspire users.

##### Remember-me?

This plug-in finds related ideas, comments and clips base upon the information of what you are working on. Remember-me search the entire Ideahub by extracted keywords and suggest connections among elemnets such as ideas, comments and clips. This plug-in can be triggered manually or run as a daemon.