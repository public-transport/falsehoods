# Public Transport Falsehoods

**Falsehoods programmers believe in about public transportation.**

> *This collection was inspired by other [falsehood collections](https://github.com/kdeldycke/awesome-falsehood) - curated lists of falsehoods programmers believe in.*

## Motivation

With some experience in reviewing or writing public transport APIs and working with data coming from [a variety of public transport operators](https://github.com/public-transport/european-transport-operators), one comes to experience the wild west of edge cases.

This list aims to raise awareness for some of these quirks both with newcomers as well as people who already spent some time thinking about public transportation - there is always something weird you didn't see yet, after all!

If you know of any falsehoods that are not included below, you're very much encouraged to contribute, have a look at the [contributing](#contributing) section of this page!

## Disclaimers

- Most examples from this list originate somewhere around Berlin, which happens to be where [@juliuste](https://github.com/juliuste) lives. If you add any points to this list, you're encouraged to use other places as examples as well!

- The naming in this list (e.g. what is a *station*, a *stop*, a *journey*, etc.) is very much influenced by the naming in the [friendly public transport format](https://github.com/public-transport/friendly-public-transport-format), you might want to spend a look at its docs.

- Most points will have some sort of *counter-example* for an assumption. Note that even if there might just be one counter-example listed, there will probably be a lot more, so you shouldn't just manually hard-code exceptions for the listed ones and expect things to be fine again

## Falsehood list

1. **A vehicle on a specific trip doesn't stop at the same [stop](https://github.com/public-transport/friendly-public-transport-format/blob/master/spec/readme.md#stop) or [station](https://github.com/public-transport/friendly-public-transport-format/blob/master/spec/readme.md#station) more than once.**

    Counter-example: Trips with some sort of circular structure, e.g. on [Berlin's circle line](https://en.wikipedia.org/wiki/S4X_(Berlin))

2. **A vehicle on a specific trip doesn't stop at the same [station](https://github.com/public-transport/friendly-public-transport-format/blob/master/spec/readme.md#station) twice or more _in a row_.**

    Counter-example: [Berlin's *Naturkundemuseum* station](https://www.bvg.de/de/standortplan/900100009) where trams stop at two [stop](https://github.com/public-transport/friendly-public-transport-format/blob/master/spec/readme.md#stop)s on the same street corner - that belong to the same [station](https://github.com/public-transport/friendly-public-transport-format/blob/master/spec/readme.md#station) and have the same name - consecutively.


3. **Vehicles never change their direction sign/headsign in the middle of a trip.**

    Counter-example: Changing the headsign is quite common in trips that run via some important hub in a city, e.g. on a line with route `A → Main station → B`, the headsign will often be `Main station` on the first part and `B` on the second part of the trip.

4. **Vehicles never change the line name in the middle of a trip.**

    Counter-example: This happens quite frequently for international trains crossing borders.

5. **A [line](https://github.com/public-transport/friendly-public-transport-format/blob/master/spec/readme.md#line) always has at least two [routes](https://github.com/public-transport/friendly-public-transport-format/blob/master/spec/readme.md#route) ("directions").**

    Counter-example: One-way circular lines.

6. **A [line](https://github.com/public-transport/friendly-public-transport-format/blob/master/spec/readme.md#line) always has a _number_.**

    Counter-example: [Paris' RER A-E](https://en.wikipedia.org/wiki/R%C3%A9seau_Express_R%C3%A9gional#Lines)

7. **Okay then, a [line](https://github.com/public-transport/friendly-public-transport-format/blob/master/spec/readme.md#line) always has a _number_ and/or a _letter_.**

    Counter-example: [London's tube lines](https://en.wikipedia.org/wiki/London_Underground#Lines)

7. **OKAY, a [line](https://github.com/public-transport/friendly-public-transport-format/blob/master/spec/readme.md#line) always has some clearly defined name.**

    Counter-example: Most long-distance connections have lines that don't have an explicit name. There are high speed trains going from Berlin to Munich every hour, which can be seen as one line, but that line doesn't really have a name passengers would clearly identify it with.

0. *probably many more falsehoods waiting to be added here…*

## Contributing

If you know of any other falsehoods not included in the list, you're very much encouraged to contribute, feel free to send a pull request or leave us a hint at [the issues page](https://github.com/public-transport/european-transport-operators/issues)! Note that, by participating in this project, you commit to the [code of conduct](code-of-conduct.md).
