This game only uses "stock characters": character tropes, such as "vampire noble" that are 
sufficiently well known and stereotyped that a typical person playing a party game can be 
given a one or two word description and know how to play that character and what kinds of
beliefs, behaviors, and tics would be "on brand" for them.

The game deliberately does not mark the gender of characters.

There are two important distinctions about characters

Primary vs. secondary characters
===============
Primary characters are potential protagonists, antagonists, love interests, and so on.
They would typically be involved in a large number of story beats.  Primary characters
are marked with by the `PrimaryCharacter` predicate.  Primary characters are defined by:
- Their `Traits` and `Interests`
- Their `WorkLife` and `WorkInteraction` scenes

Secondary characters are walk-on characters used to advance a plot point and then discarded.
They are marked by the `SecondaryCharacter` predicate.

Characters vs. cast members
============
A character is someone who can potentially participate in a story.  Characters are marked by
the `Character` predicate.  However just being a character does not mean they appear in
any given story.

A cast member of a story is a character who appears in that story.

`CastMember` is true when its argument has been cast in the current story, and false if
they either don't appear in the story, or at least have not yet been cast for the story.
It can also be used to enumerate the members of the cast by passing it a variable as
an argument.

`Cast` is like `CastMember` except that when called with a variable as an argument, it
selects a new primary character who has not yet been cast in this story, adds them to
the cast, and binds its argument to that character.

So basically, `Character x` means `x` is _available for use_ as a character, `CastMember x`
means they're actually in use as a character, and `Cast ?x` means "give me a new primary
character not already used in this story."