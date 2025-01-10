# Gaem

## so what game?

I want to take ideas from Warframe, Destiny and WOW and pick the good stuff, at least from my POV. The visuals would be almost-isometric Hades-like and the combat system also inspired by Hades, with mixed in elements of souls-like gameplay.

It would be a co-op with variable team size of 1-N (N could differ based on gamemodes, maybe 2-8). Content would scale accordingly.

## wtf do I do in the game?

Well, collect stuff, improve your character to complete increasingly harder content (or do it faster).

## so how does it actually play?

There would be `hubs`. Could start with just one. New game updates would bring new `hubs`. Each `hub` would have its style (I'm not even sure what the overall aesthetic or setting of the game should be tbh) akin to warframe/destiny's planets - Earth, Venus (probably won't be planets, though). `Hubs` would be a place to meet players that are looking to do content in that area.

This content would be `expeditions?` - exploring adjacent areas of the hub that are not as friendly. Each `expedition` would be a semi-proceduraly generated instance (we'd have pre-made set of `tiles` that we connect together to form the `map`).

Each `expedition` would have its own objective, there would be 3 `types` of objectives.

1. In-and-out - Short, straightforward objective (eg. kill x enemies in the `map`, retrieve an item from a guarded vault, etc...)
2. Endless - Endlessly repeating objective with increasing difficulty (for example kill waves of enemies, defend an objective). After each wave, the players would have the option to leave or stay another wave, accumulating rewards.
3. Dungeon - basically a boss fight with some added extras, maybe side objectives before reaching boss, etc. Defeating a boss would drop a `key` - more on this later.

> Note on endless is that I'd like to dis-incentivise super long runs - maybe even drop endless altogether? or just make it capped at N waves? If we just make scale hard, people will find a way to beat the scaling, I've played enough games to know that much.

**so what incentivises me to do these expeditions?**

Well, it's the core gameplay loop. More specifically, though:

- Successufully completing an `expedition` rewards a `hub`-specific currency. The drops of this currency are capped daily (this incentivises daily logins.), perhaps even capped per-`expedition` `type` as this would incentivise playing different `types`, not just spamming the "meta" one. This currency lets you:
  1. Increase `reputation` with the `hub`.
  2. Buy `hub`-specific items. Weapons, Gear items, consumables, cosmetics - whatever.

## random thigns I thought of but there's not enough context

**Concept of `upgrades`**

Any `upgrade` for character should be interesting. I know this is vague but what I mean is - it should not just upgrade base stats. Base stats upgrades will be handled through `power level` alone (more on this another time). These upgrades should create synergies with interesting effects. For example:

- Let's say we have some notion of a "mage" character. Mage has 2 abilities. Fireball and Blaze. Fireball is just a single-target projectile. Blaze is a short buff that makes all fire damage crit - sounds very basic, I know. Now let's introduce some "upgrades".

  - Example of a "bad" "base stat" `upgrade` - Fireball deals more damage (ew). Blaze lasts 2 seconds longer (ew).
  - Examples of "good" `upgrades`:

    1. Casting "fireball" on a target accumulates a "flamed up" debuff. This is a DOT effect that ticks every 1s and is calculated as "fire damage dealt to target in last 5 seconds \* multiplier".
    2. When "blaze" expires, current state of "flamed up" debuff is transferred to all enemies withing x meters.

> This creates a synergy where we transform a very basic kit ("fireball" and a crit buff) into something that can clear masses of enemies, especially in situations where there's multiple smaller enemies around a "bigger" one. You could use the "big" enemy as your single target proxy to spread the debuff to all the smaller ones, instead of killing small ones one-by-one. Also promotes skill and knowledge based gameplay - do I have the window to cast as many fireballs as possible in my blaze window? Is the "big" enemy going to summon many small ones in a couple seconds?

I guess what I'm trying to say here, these `upgrades` should be gameplay-altering instead of flat stat buffs.

**Concept of power level**

This is a way to battle power creep over time in the game. Honestly I myself only have a vague idea on how to implement this. But in essence:

- each `expedition` would have a `power level` assigned to it.
  - basic `expeditions` accessible directly through the hub would have `power level` equal to the season minimum??
- via various activities, players would gain `power level` up to a (seasonal?) cap.
- instead of players doing more damage with their `power level`, we take the relative difference between the `expedition` `power level` and the player `power level`.
- `damage multiplier = e ^ ((player_pl - expedition_pl) / 15)` - random formula I crafted, exponential scaling means you can breeze through lower `power level` `expeditions` and `expeditions` that are higher are way harder, or impossible to complete. This however brings issues.
  - We should restrict rewards from `expeditions` that are way below the player's `power level`
  - Issue of "bussing" lower `power level` players through missions is an issue - maybe restrict entry if the difference is too high altogether.

`Power level` is just average of armor and weapon `power level`. Weapon `power level` likely weighted slightly higher.

**Concept of `seasons`**

Game being `seasonal` would keep players invested regularly. It would alleviate the notion of "having completed the game" (at least every now and then).

- each `season` would bring new content to the game. New `hub`, new system to interact with, new weapons, new characters? - maybe a selection of said things.
- `power level` cap and floor would reset each season. Meaning players would "keep their stuff" but this "stuff" would have to be brought up in `power level` again and upgraded via the `season`-specific systems.
- old `season` upgrades would become ineffective (or less effective) - random idea - give each upgrade a `power level`, too, and cap it at that `season's` cap.

How do we deal with `power level` creep? Or is this concept future proof enough? If each `season` has +100 `power level` increase, and a `season` lasts for about 6 months, we'd have plenty of time before it gets to "weird" levels.

We'd need to balance the `power level` gain against hours of playtime needed. Maybe it would be exponential as well. For example (if `season` increase is 100), getting to +50 would take a couple of hours, giving the player dopamine and motivation to keep going. Then getting to +90 would be a considerable jump, requiring more time and harder content. Bridging the +90 to +100 gap would only be for the "power users", sinking 100s of hours of playtime each season.

**Concept of `keys` and reviving previous `season` content**

Irrelevant content is bad for the game. New `season` should introduce new content but not entirely make old content obsolete.

Let's say we're in the second season. Base `expeditions` in the `hub` are `power level` 100. Defeating a base Dungeon `expedition` boss awards a level 1 `key`. This is is for a random set of N `expeditions` from any of the `season` `hubs` (basically any `expedition` in the game). Last `expedition` on the key would always be Dungeon `type` of that given `hub`. This `key` lets you run those specific `expeditions` at an increased difficulty. Let's say `base_pl + key_level * 5` so in this example, `power level` 105.

You can share this `key` with other players, entering these `expeditions` back to back. These `expeditions`, along with the increased difficulty, will be somehow failable. Let's say normal "kill all enemies in the map" `expedition` doesn't have a timer but this one would. Same for the Dungeon `type`. There are now multiple outcomes:

1. Players fail the timer (or any other extra conditions), but succeed in finishing.
   - This will reward lower level loot (random math: `key_pl - 10`)
   - drop the `key` level by 1 (if possible, keys won't get destroyed and 1 is minimum)
   - it will also re-roll the key to another set of `expeditions` from another `hub`
2. Players fail altogether, not finishing the `key`.
   - this will reward no loot
   - drop the `key` level by 1
   - **not** reroll the set of `expeditions` on the `key`
3. Players succeed in finishing and beat the timer (or any other extra conditions).
   - This will reward loot at `key_pl - 5` (why -5 is important for endgame, I think. might not be -5 but definitely should be lower than `key_pl`)
   - increase the `key` level by 1
   - reroll the set of `expeditions` to another one, from a different `hub`
4. Players succeed with honors (beating timer by a lot, completing some "hard mode" or similar)
   - Same as 3. but `key` level increases by N instead

The `key` level will be uncapped. Players can go as high as they please, want or are able to. Reward `power level` will however eventually cap at the `season` max. If we consider that each `key` drop rewards at `key_pl - 5`, rewards would stop scaling at level 21 `key`, or in this example, 205 `power level`. Note that this is higher than the `season` max `power level` so the scaling formula needs to be adjusted here.

NPC in the `hub` will be providing service to drop your `key` by 1 level, but reroll its `expedition` set.

> This could have some notion of weekly rewards based on how high keys and how many you've completed. Maybe cap direct key rewards at lower power level and you'd only get to max power level through these weekly rewards.

## you keep talking about rewards, what do I actually get here? how do I even know what to do?

Let's start from the beginning. It's `season` 2 and I'm a new player. I log in, I choose my character. Mandatory introduction quest starts. I'd envision this taking somewhere between 30 minutes and an hour. This quest showcases some evergreen systems and gameplay. It is entirely solo and it takes place in the current `season` `expedition` (or maybe have stable ones? idk) maps scaled to the exact player `power level`. Over the course of this quest, you're awarded some starting gear, raising your `power level` to the `season` floor -5, in this case, 95.

You're then thrown out to the current `season` `hub` to look around. Different NPCs will want to talk to you and tell you what the heck you're supposed to be doing - `expeditions`. You do enough of `power level` 100 expeditions to get some currency, you team up (or not...) and beat the base Dungeon. You have a 105 `key` and some currency now. NPC tells you all about the `keys`. You first go to the `season` gear vendor and buy all the pieces (after running some more missions because you didn't have enough currency). This gear is 100 `power level` and it will take you through the entire `season`. If upgraded. Players who played in the previous `season` could just trade their upgraded gear pieces for the new `season` gear directly.

You can also vendor for `season` specific `character upgrades` at 100 `power level`.

You them team up (or not...) for your first `key`. You complete it just in time and you get a 100 `power level` `gemstone` - 100? that's useless! I already have 100 `power level` gear. That's fine - gemstones can be merged into higher tier ones, to up to a cap (more on this later). Anyway, you also get a 110 `key` now! And you get a `character upgrade` (as talked about previously) from the reward pool of that `season` at `105` power level!

You succesfully complete your second `key` and get a 105 `gemstone`. Now let's head to the smithy and apply this `gemstone` to one of our `season` gear pieces. Voila! Your're now slightly stronger and can have a shot at your 115 `key`.

Repeat.

> Gemstones could be for armor and weapon separately. Weapon ones being more valuable.

> We need an incentive to team up. Perhaps each person in a squad provides a key (the condition is just the same key level or higher). This will the roll the reward table of the key N times and people can pick 1 reward each, reducing RNG. This however introduces the issue of "meta" keys where if you have a key you don't like, you just look for a person who has the one you need and merge with that one.

**Note on gemstone merging**

You can merge N lower `power level` gemstones to 1 higher `power level` gemstone. For example, I can merge 2\*100 into 1\*105. 3\*120 into 1\*125. This merging would, however stop at around 150. It would just be a system to help with the first +50 `power level` gain.

What the heck do I do with the 1000 150 `power level` gemstones that I now have? Useless! - good point, need to figure out a use for them. Perhaps trading? oh right, trading - haven't even touched on that. But yes, I'd like to include some player-driven economy.

## ok but why do I repeat the same shit over just to increase a number?

Well what are games other that this exact thing, amirite?

The competitive element of completing hard `keys` fast can be transformed to ingame leaderboards, with rewards for `season's` best players. Who doesn't want that exclusive title, or a shiny new badge, or a skin? And the fame, man, the fame of being among the best.

Of course, the graphics, the gameplay, the combat, the balance - all would be incredibly important in order to keep players interested.

> Power level is nice but it blurs the line between someone who's played for 1000 hours that season and someone who's played for 2 hours. They still see the same numbers, similar gameplay, but the `expedition` `power level` is just... higher. **There needs to be nother power-progression, gameplay-altering system in place** specifically to address this issue - Perhaps higher level keys would actually drop other than the basic gear items that would have some special effects, look different, alter gameplay.

> Dev organized tournamets of who completes tough keys faster with live streams would be amazing here. Our own esports.

## are there some shiny items for me to get?

Perhaps, this is largely TBD. There could be some rare drops from say level 20+ `keys` that can then be crafted into the `season's` legendary item, that would have a slight boost in `power level` over the `season` cap and some extra effect.

## how the hell do characters and their gearing work?

Vague idea but. Same gear on different characters would have different effects. It would also be transferrable. Or universaly usable within that account. Meaning you can swap character at any time - you would just have to collect new `character upgrades`.

Same with weapon.

## is there a notion of account progression? or new account in a new `season` is basically identical to a veteran one?

Well that's a tough question. I want `seasons` to be a reset in player power. Not a fan of giving old player a significat advantage. Perhaps some stats associated with the account to show how much the player has played in different seasons. Perhaps an account "level" that increases the more you play over time, or based on how many of the game's items you've collected.

## what is the MVP?

- 1 hub with a couple in-and-out missions and a Dungeon
- couple playable characters
- some upgrades
- key system working
