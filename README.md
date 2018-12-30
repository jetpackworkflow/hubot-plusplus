hubot-mega-plusplus
==============
Forked from the original [hubot-plusplus](https://github.com/ajacksified/hubot-plusplus).

Give (or take away) points from people and things, all from the comfort of your
personal Hubot.

What makes (or will make) this different from the original hubot-plusplus?
- Aims to incorporate some of the features of the Hipchat Karma bot
    + Flexibility of input (arbitrary text before/after "thing++")
    + Add and remote multiple points at once
- Admin support
    + Only admins can erase things
    + Set arbitrary point values for things

API
---

* `you are the best thing++` - add a point to `thing`
* `'taco tuesday'++` - add a point to 'taco tuesday'
* `++` - add a point to the most previously voted-on thing
* `thing++ for stuff` - keep track of why you gave thing points
* `thing--` - remove a point from `thing`
* `--` - remove a point from the most previously voted-on thing
* `thing-- for stuff` - keep track of why you removed thing points
* `hubot erase thing` - erase thing from scoreboard (permanently deletes thing from memory)
* `hubot erase thing for reason` erase given reason from thing's score board (does not deduct from total score)
* `hubot top 10` - show the top 10, with a graph of points
* `hubot score thing` - check the score for and reasons for `thing`

Uses Hubot brain. Also exposes the following events, should you wish to hook
into it to do things like print out funny gifs for point streaks:

```coffeescript
robot.emit "plus-one", {
  name: 'Jack'
  direction: '++' # (or --)
  room: 'chatRoomAlpha'
  reason: 'being awesome'
}
```

## Installation

Run the following command 

    $ npm install hubot-mega-plusplus

Then to make sure the dependencies are installed:

    $ npm install

To enable the script, add a `hubot-plusplus` entry to the `external-scripts.json`
file (you may need to create this file).

    ["hubot-mega-plusplus"]

## Configuration

Some of the behavior of this plugin is configured in the environment:

`HUBOT_PLUSPLUS_KEYWORD` - alters the word you use to ask for the points, default `score`.
`HUBOT_PLUSPLUS_REASONS` - the text used for the word "reasons" when hubot lists the top-N report, default `raisins`.

