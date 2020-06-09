# A Philosophy of Software Design

Some of my notes about the presentation from John Ousterhout https://www.youtube.com/watch?v=bmSAYlu0NcY


> "Software design still a black art."


How are we not just teaching the most useful and primary tools that we use when programming like "problem decomposition" and "abstraction". Is that even possible?

There is a study that says that the only thing that correlate on the most things that people think that is based on talent is the number of repetitions. So the only way to make good code is by practicing. And today the student just do some crap code to get the degree and than, when he becomes a teacher he just stops doing so. 

## The course

John created a new course in Stanford to teach like the way you teach english in high school: with a iterative approach. So you write and send to teacher to review. 

After the review you rewrite one more time and give again for another review and so on. So the student build a large system from scratch in 3 weeks. After this the code is reviewed and the student keep improving the code for more 3 weeks based on reviews and teacher meetings. Then, after another 3 weeks, the students starts from scratch again another system.

## The secrets

Things that the professor found by reviewing and iterating the course many times.

### Classes should be deep
The ideal class has a small interface complexity, but larger functionality. So it should abstract all the things that it does.

it totally disagrees with the common wisdom that _"classes and methods should be small"_. Maybe the developer later just wants to create a simple thing, but she has to create a enormous amount of variables to use the thing properly. You want to make the common case simple!

> Length isn't the bug issue, it's abstraction

**Question**: Será que isso se aplica também a apis que as pessoas nao usam com funções diretamente?

### Define errors out of existence

Exceptions is a huge source of complexity, but today is taught to throw as many errors as you can. But there is a better approach to this: we can redefine semantics to eliminate exceptions. Maybe it should not be an error, but a side case. You can redefine something that were an error to something that is fine and expected, but don't crash the system.

Example: to remove a variable that do not exist we can, instead of just throwing an error, just do nothing if this do nothing. Or Get a substring that has a index out of the bounds of the initial string.

Sometimes when we start to add a lot of checks to keep the user from doing the wrong thing, we make the whole method just complicated to do the right stuff.


### Mindset: Tactical vs Strategic Programming

The tactical (most used) has as goal to get the next feature/bug fix working ASAP and do it even with bad design and high complexity, but complexity is incremental. It's the easier way to go

But I gotta think that working code is not enough. With the Strategic mindset the goal is to produce a great design and simplify future development. So you should take an extra time today but it pays back tomorrow.

> Working code isn't enough.

But how much to invest? You must ask yourself how much are u able to afford. SO when writing new code you should think carefully about design and do some good documentation and Unit tests. And when changing existing code you should always find something to improve.

**Question**: Quando é que eu sei quando o que eu to fazendo é Strategic ou se eu estou indo muito longe e pensando demais? Ele comenta um pouco a respeito disso, mas é dificil de vc saber ate quando continuar pensando a respeito.
