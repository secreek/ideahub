#IdeaHub

*Implementation spec for Phase No.1*

*Please read spec.md first*

## Basic Thoughts

The first phase of IdeaHub is based on Git, the version control system that is developed by Linus. We choose git because of the shining features of `Distributed VCS`, `Fork`, `Pull-request` and so on. 

For example, we can `attach` the `File` or `Clip` to the idea by staging them into the repo, and set some `Milestone` or `Tombstone` by adding some tags. The `Notification` feature can be easily implemented with the help of `git hooks`. Even better, `Forking`, the key feature of ideahub will be out-of-box thanks to git. 

By version controlling the ideas, you can easily analyse & visualize (with the help of GiTalk, maybe) the revolution of ideas when the product is shipped. By putting the ideas in a specific git branch, say `branch-ideahub`, you won't need to worry about our hub polluting your code branch, we will only mege the result of discussion to `master` branch at your call.

The following list displays the basic ideahub-to-git mapping:
- Idea => Git repo
- File & Clicp => Files staged in the repo
- Connection => Staging in repo
- Milestone (Snapshot) => Git tag
- Tombstone => Also a git tag
- Forking => Repo forking

The features can not be mapped to git but will be implemented in this version are:
- Comment
- Star
- Voting
- Notifications, with the help of git hook
- Taging, not the same tagging in git
- Idea status

## URI(??)
The uri for specific ideas in the ideahub, for example:

    idea@ideahub.com:void-main/SomeFreakingIdea
    
You can use `void-main/SomeFreakingIdea` for short.


## Interfaces

In this version, we will focus on functions rather than interactions, so the major interface will be the CommandLineInterface(CLI). On the other side, we will implement the web server exposing the RESTful APIs.

### CLI options
The command name will be `ideahub`, the basic usage is like the following:

    $ ideahub usage
    
    Thanks for using ideahub to share, discuss and develop your ideas.
    
    Usage:
        
        ideahub command [arguments]
        
    Commands:
    
        new        :: Create a new idea on ideahub. The argument will be the name of the idea. Optional arguments will be `--tag comma-seperated tag names`.
        explore   :: Explore someone else's idea. Use `--tag [tag_name]` to explore ideas with some tag, `--name [repo_name]` to explore only the ideas that matches the name.
        fork        :: Fork someone else's repo. The argument is the uri of the idea.
        star        :: Stars a specific repo. The argument is the uri of the idea.
        vote       :: Votes for a specific repo. The first argument is the vote action, upvote or downvote, the second argument is the uri of the idea.
        tag         :: Use --add [tag_name] or --remove [tag_name] to add or remote tags.
        milestone :: Add a new milestone/snapshot.
        tombstone :: Put the idea to the tombstone.
        publish    :: Push the idea up to the hub.
        
## Some questions

### Expose git repo or not?
Granting access to git repo may lead to unnecessary problem for users. However, it is the most efficient way to edit the idea. If we don't grant access, we'll have to implement a whole set of edit tools for end user to work on the idea. This is a tough choice.

### Wrap git commands if we decide to expose git repo to users?
Shall we wrap common git commands, for example, the `tag` command in git is completely different from the `tag` command in ideahub. Shall we redefine a set of vocabulary for ideahub?

