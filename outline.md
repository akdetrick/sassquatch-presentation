# NYC Sass talk

Working with legacy CSS using the Stranger Vine pattern and custom CSS foundations/frameworks


## The problem
- "@akdetrick myself three months ago is a complete stranger." [tweet](https://twitter.com/beatak/status/311963302756495361)
- design consistency
- reinventing solutions to problems that have already been solved
- overly specific CSS that's nearly impossible to reuse (even when something is visually similar)
- lack of a canonical way to accomplish any given layout task
- unending cycle of code bloat
- starting clean is not an option

## What doesn't work
1. Brief intro to TSC problems (page-by-page 150kb css files, compressed)
2. Proposed solution: brand new tiny CSS foundation, with 80% weight reduction
3. Incredibly positive response from management and dev team
4. Required huge rewrites of templates. 1 year passed without starting implementation because taking 2 months to rewrite everything is never an option


## Strangler Vines

#### Botanic definition
- type of tropical plant with an adaptation for a light-competitive environment
- seeds at the top of a living tree
- grows down the host tree trunk
- invades host tree roots
- eventually strangles the host tree, killing it
- once the host tree is dead, the strangler vine is essentially a freestanding hollow tree

#### Images
1. Seeding ![edrabbit](http://farm9.staticflickr.com/8205/8251868992_c9a35bf025_h.jpg)
2. Strangling ![nancybaym](http://farm4.staticflickr.com/3503/3828905896_e13528bbbf_b.jpg)
3. Rooted ![laughingface](http://farm2.staticflickr.com/1040/956891083_ceba98c386_o.jpg)
4. Freestanding ![anitagould](http://farm6.staticflickr.com/5018/5501316782_4be0a28ccf_b.jpg)


## Strangler vine patterns in CSS
[original idea](http://martinfowler.com/bliki/StranglerApplication.html)

> ... gradually create a new system around the edges of the old, letting it grow slowly over several years until the old system is strangled.


> The most important reason to consider a strangler application over a cut-over rewrite is reduced risk. A strangler can give value steadily and the frequent releases allow you to monitor its progress more carefully.


> ... when designing a new application you should design it in such a way as to make it easier for it to be strangled in the future. Let's face it, all we are doing is writing tomorrow's legacy software today.

#### Strangling CSS
Replace the top of the cascade with a solid foundation based on deliberate design decisions. The foundation is essentially a [style tile](http://styletil.es/) expressed in code.

- new "normalize" css
	- typography, element defaults, etc. styled to a standard design
- layout system
	- grid system, oocss grids, gumby, etc.
- common markup/style patterns
	- media blocks, lists, etc.
- modifiers
	- for nudging things that defaults don't handle
	- note about the semantics/performance of extends vs. oocss style classes

#### The plan
1. "seed" the top of your cascade with a new foundation (this can be done without breaking much, since the cascade will overpower your foundation at the beginning)
2. Document! The foundation isn't useful unless it's easy for any developer to understand
3. Allow your foundation to replace more and more of the legacy css by refactoring markup (it's useful to have a switch for legacy/modern base css)
4. Use the tools and defaults the foundation provides to build new features (instead of writing new css)


## Meet Sassquatch
Sassquatch is a CSS foundation/framework written for Meetup, and acts as our strangler vine.

#### Guiding principles
Explain some things from our ["Rational CSS" manifesto](https://gist.github.com/akdetrick/ecf02a18c0e36ad3b1b7)

- Design first
- Go with the (document) flow
- Avoid ancestry
- Explicit is better than implicit
- Small, sharp tools

#### The code
Explore the [repo](https://github.com/meetup/sassquatch) a bit.
Show [documentation](http://meetup.github.io/sassquatch/).

#### The future
Show our new "style tile", and explain how Sassquatch bridges the gap between design and development.
