# Night City Rivals: Dialogue

This repo contains all of the dialogue for the Night City Rivals mod!

The dialogue in this repo is done via the in game texting interface, NOT face to face dialogue, so there's no need for voice acting.

## Contributing

Anyone can add lines, replies or new personalities through a pull request. Read [CONTRIBUTING.md](CONTRIBUTING.md) for how to do it, what makes a good line, and what won't be merged.

## Structure

The repo is structured in a specific way that allows me to import the dialogue into the game. Doing something outside of this structure won't work, so don't do that.

The structure is simple:

```{personality} -> {event}.md```

A personality is the speech style a rival can roll when its created. For example the "Yapper" personality texts way too much, often double texts, and narrates their actions. On the other hand, the "Laconic" personality texts in short terse texts.

The "Event" is something V did to trigger the message from the Rival.

The big ones implemented right now are:

* Flatlining V
* Surviving being flatlined by V
* Ambushing V
* Killing a rivals rival.
* Killing a rivals lover
* Killing a rivals sibling
* Ordered Hit from a higher up
* V evaded the rival


## Event Page Structure

The event pages hold all the dialogue in the mod, and who can say it.

First part is a description of the event for context.
Second part is what factions can say the lines, "Generic" is any faction, and the other options are the different gangs. Keep in mind that only Maelstrom is implemented in the mod so far which is why only generic and maelstrom are filled out.

## Dialogue structure


The dialogue is structured in trees, with the root being what the rival said, then the reply under it, prefixed with `V:` is what V can reply in game.

Syntax:

```
- Hi, welcome to FūdHouse, what can I get started for you?
    - V: I'll have a cheeseburger and fries
        - That will be $5
            - V: here you go
            - V: Nevermind, too much
            - V: Actually...
    - V: I'll have nuggies
        - That will also be $5
        - Can I get sweet n sour sauce with that?
    - V: Nevermind
        - Ok then

```

If there are multiple options, the game will pick randomly during runtime, for example this tree will choose between any of those three lines.

```
- Hi, welcome to FūdHouse, what can I get started for you?
- Hi, welcome to afterlife?
- Hi, welcome to mac and cheezus.
```

## Substitutions

Words in `{braces}` are swapped for the real thing when the text is sent.

### Who's texting

| Write | Becomes | Example |
|---|---|---|
| `{name}` | The rival's handle | Rivet |
| `{title}` | Their title | the Butcher of Northside |
| `{rank}` | Their rank | Lieutenant |

### Who they're texting about

| Write | Becomes | Events |
|---|---|---|
| `{partner}` | Their lover or sibling's first name | flatline-lover, flatline-sibling |
| `{enemy}` | Their own rival's first name | v-killed-rival, hired-hit-v |
| `{ENEMY}` | The same name, IN CAPITALS (for shouting) | v-killed-rival, hired-hit-v |

The rival they hate is `{enemy}`, not `{rival}`, because "rival" already means the person texting V.

### Pronouns for that person

These follow `{partner}` or `{enemy}`, whichever the event is about. Write both words with a slash, and the game keeps the one that fits.

| Write | Becomes | Example |
|---|---|---|
| `{she/he}` | she or he | No {she/he} didn't. |
| `{She/He}` | She or He, for the start of a sentence | {She/He} never listened. |
| `{she's/he's}` | she's or he's | Now {she's/he's} gone. |
| `{her/him}` | her or him | You broke {her/him}. |
| `{her/his}` | her or his | Running {her/his} mouth. |

### Event details

| Write | Becomes | Events |
|---|---|---|
| `{weapon}` | The weapon V beat them with last time | ambush-v |
| `{count}` | How many rivals were in the group V got away from | v-evade |
| `{eddies}` | The payment, formatted (e.g. 12,000 eddies) | hired-hit-v |
| `{place}` | Where the target is, e.g. "at the Underpass" | hired-hit-v |

## Stat Triggers

We can raise or lower heat from the dialogue too. Heat is from 0-100.

There is two types of heat, faction wide and individual. Individual heat is gained or lost by via dialogue or by flatlining relatives/chooms.

You can increase or decrease it via the ``[brackets]`` at the end of V's replies. They don't do anything in Rivals dialogue.

Examples:

```
V: Hi, are you the butler or something? [personal]
```

This raises the personal heat level of the rival by 1. You can also add a number to add more heat. For example it increases by 10 if you add +10

```
V: Hi, are you the butler or something? [personal+10]
```

Use faction instead to raise faction heat levels:

```
V: Maelstrom sucks [faction+100]
```

Note: I don't use faction at all as it is very easy to raise faction wide heat level through just regular gameplay.

## Dialogue Checks

If you want a skill check (I don't use any of these yet), just add `[stat #]` to the dialogue.

```
- V: I'm Mr.Cool [Cool 9]
```

## New Personalities

If you want to create a new personality, just copy the template folder and fill in the lines. I'll be able to map that as well.