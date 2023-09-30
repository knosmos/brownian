<!--
.. title: Floating Point Errors
.. slug: floating-point-errors
.. date: 2023-08-10 23:10:34 UTC-04:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text
-->

*Written after a very frustrating debugging session*

Absolutely screwed.

After analysing my situation in great detail and considering all possible courses of action, that is my informed conclusion. Utterly completely positively screwed.

<!-- TEASER_END -->

It was assigned a month ago, but the human mind is a master at refusing to get things done. At first I had decided that two weeks would be enough to finish it, but as the time ticked down I convinced myself that two days would be sufficient. Reality only kicked in the night before the 8:00 a.m. deadline, when I realised that I had yet to start. As it turns out, inertia not only applies to physical objects, but also to our brains.

But what to do? The project was worth twenty percent of the final grade. If I didn’t at least try... well, considering my current track record, let’s just say that I would’ve been in for a hell of a hard time. So I got to work.

And that, my dear friend, is how I found myself at two in the morning, eating a bowl of Cup Noodles brewed with cold coffee. It’s not as bad as it sounds. Well, it actually is about as bad as it sounds, but the dorm’s kettle was broken and taste buds are a lot more forgiving when you’re desperate for something to eat ― hence why I decided that at this time and place it was socially acceptable for me to mix instant noodles with the cup of coffee left on the kitchenette counter from two (or was it three?) days ago. I was probably committing some sort of culinary war crime in the process, but I was far beyond caring.

The midterm project of *Introduction to Orbital Mechanics* was to make an n-body simulator. The assignment was not particularly difficult, or so I thought; a perennial problem in physics is that everything is harder than it deserves to be. Actually, that seems to apply to life in general as well.

An n-body simulator models the behaviour of multiple dynamic particles acting under the influence of gravity. So, for example, it can model the planets as they move around the Sun. Simple enough, right? Just some basic applications of Kepler’s laws of planetary motion. Except each of the objects is also acting on the others ― the Sun pulls on Jupiter, but Jupiter also pulls on the Sun, and Jupiter also pulls on Mercury and Venus and some random comet hovering at the edge of the solar system. With some clever differential equations and analytic integration, that’s all solvable, just really annoying to code.

By four in the morning I had managed to get through the maths, and with some “creative interpretation” of other peoples’ code, I had a working program. Well, for a limited definition of “working program.” Everything seems normal at first, but run the simulation for a few minutes and things start to seem a bit off. Planets start jittering in their orbits. Comets are flung around at twice the speed of light. Moons flicker out of existence.

The problem, it turned out, was floating point errors.

Floating point representations are a clever trick that programming languages use to store really large and really small numbers. To explain it simply, there’s a significand, which stores the “number” part of the floating-point number, and an exponent, which indicates how many places the decimal point should be moved to scale the significand.

The only problem is that the significand can only store a certain number of significant digits; eventually, you have to start rounding. And eventually, those rounding errors start to add up. The larger the number, the greater the imprecision. And when we’re talking about numbers on the scale of solar systems, those numbers are really large. You can’t just make everything smaller, either. The professor demanded that the simulator be scaled to real-world proportions, and the tiny moon Phobos orbits Mars at a distance fifty thousand times smaller than Mars’s own orbit around the Sun.

At this point it was five in the morning. There are times to aim for perfection, and there are times to aim for “good enough.” And, well, this was one of those times where it was better to aim for “good enough.” Hopefully, whichever poor TA got to grade my project wouldn’t look that hard at it. I hit submit and went to sleep.

Or at least, I tried to. It was probably a bad idea to eat coffee-infused instant noodles at two in the morning. I couldn’t sleep. The caffeine racing through my bloodstream refused to calm down, throwing my mind about in a turbulent flow of thoughts.

I figured I would go on a walk. Something to clear my consciousness. Something to distract me from the differential equations and the fact that my virtual Phobos teleported in its orbit every few seconds. And hell, maybe I’d figure out how to solve it. Inspiration strikes when you stop trying to make it strike so hard.

On a whim, I climbed the staircases of the dormitory, the cold autumn breeze brushing aside my hair as I creaked open the rooftop door. I was woefully underdressed for the weather. My arms involuntarily wrapped themselves across my chest ― and yet inexplicably I kept walking across the rough concrete roof, looking at the night.

The heavens were clear.

Slowly the universe flickered into focus as my eyes adjusted to the darkness.

Serenity, at last. 

There was Polaris, shining steadfastly, guiding my eye towards celestial north in the same way it had aided navigators for millennia before. There was Sirius, the brightest pinprick in the night; a binary system, two stars waltzing around each other slowly, appearing as a single faint dot in the stellar canvas. There was Rigel, a massive giant a hundred thousand times brighter than our Sun, its light reaching my eyes after an odyssey of nearly nine hundred years. There was Vega. Canopus. Antares.

I remembered looking up at those same stars as a child ten years ago. I remembered those innocent eyes straining to trace the path of the constellations. I remembered staring at the darkness through my telescope, the earthy scent of petrichor wafting through the night air. I remembered why I had first found an interest in physics, why it had ignited a passion within me that once seemed to burn as brightly as the galaxies themselves.

For a moment the cosmos seemed to align in a perfect dance of celestial motion, carefully choreographed by the forces of gravity.

Then I saw a star fall out of the sky.