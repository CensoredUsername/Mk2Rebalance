# Mk2 Rebalance

This mod attempts to fix the frankly awful balancing of the Mk2 spaceplane parts in KSP1 by bringing them more in line with the other parts in the game.

## The issues of Mk2 spaceplane parts

Mk2 spaceplane parts have two major issues.

First, they are incredibly draggy. An Mk 2 fuel tank at Mach two and a 5 degree angle of attack, with both nodes completely occluded, will generate twice as much body drag as a 5m rocket tank of equivalent length. This despite the 5m rocket tank containing 16 times as much fuel.

Second, they are very large for the amount of fuel they store. An mk2 spaceplane part has more than twice the cross sectional area of a normal 1.25m fuel tank, but store the same amount of fuel. In fact, the cross sectional area of Mk2 spaceplane parts is more in line with the area of 1.875m tanks, which store 2.25x the fuel per unit of length.

These issues are contrasted by their apparent advantages. Mk2 spaceplane parts generate a small amount of lift (about equivalent to 0.04 tons of wing per standard length), and they have a higher temperature tolerance of 2500K vs the normal 2000K.

Unfortunately these advantages just don't weigh up against the presented issues, and it is possible to get equivalent parts by combining fairings, normal fuel tanks and normal wings which do not have the previously mentioned drawbacks.

So to summarize: normal Mk2 spaceplane parts have the tank capacity of 1.25m tanks, the volume of 1.875m tanks, take up the space of 2.5m tanks, and create more drag than 5m parts, for the benefit of having worse temperature tolerance than a fairing, and a tiny bit of lift that cannot be effectively used. 

## What causes this and how do we fix it

The low fuel loading of these parts seems to just be derived from the equivalent 1.25m parts. In practice, this leads to it being very inconvenient to build spaceplanes using Mk2 parts as you can fit two 1.25m parts in the same space as a single MK2 tank.

This mod changes these parts to contain 60% more fuel (and be 60% heavier) to rectify this. The choice of 60% was made to offer some amount of drawback to their use still, and to offer a realistic compromise between their true volume, their suboptimal tank shape, and the need for some amount of space for the thermal protection system.

The drag issue has a more complex cause. When KSP evaluates the drag cubes for the Mk2 parts, it observes that their top and bottom are very flat, and as such assigns a very high drag coefficient to them (~0.90, compared to the normal 0.77 for cylindrical tanks). KSP's drag model penalizes drag coefficients above 0.85 extremely heavily over those below 0.80. When flying at any angle of attack, the top or bottom surface of the part gets incorporated into the drag calculations, and the drag of these parts spikes. This effect is so bad, that opening Mk2 payload bays can actually reduce the drag of these parts as it causes the drag model to evaluate them as less flat, even though their cross sectional area almost doubles.

This of course doesn't make sense. These are supposed to be spaceplane parts, optimized for low drag. They're shaped like wings for a reason. so why do they not perform as such? It turns out wings have custom drag handling that avoids this problem of normal KSP part drag calculation. But this is not used for the Mk2 parts.

So what this mod does is to tweak the drag cubes for mk2 parts a little to make the parts have similar drag as 1.875m tanks at low angles of attack. This is simply done by reducing the top / bottom face drag coefficients to ~0.72. It also enables the wing drag calculation code for them, so they still provide high drag at extreme angles of attack, like you'd expect from a wing.

These changes are very minor, but they have incredible effects on the handling of Mk2 style spaceplanes. It is no longer needed to give wings an angle of incidence, you have much better glide slopes, and maneuvering loses much less speed. Stability is generally also closer to what the centre of pressure indicator would suggest in the SPH. The higher fuel loading also means spaceplanes become significantly smaller with the same fuel loading, bringing them more to scale with rockets of similar performance and actually making it possible to create high-performance Mk2 spaceplanes without resorting to normal fuel tanks to keep their size under control.

## Requirements

This mod requires ModuleManager.

## Compatibility

This mod purely changes the basic stats of some stock parts, so compatibility is assumed to be quite broad. That said:

- Regarding FAR: Any of the aerodynamic changes made by this mod will probably not work under FAR, but as FAR implements a completely different aerodynamic model this shouldn't be an issue.

- Regarding mods that add more Mk2 spaceplane parts: These will need custom handling to combine with this mod. I am planning to at least add compatibility for Mk2 Stockalike Expansion, but for now those retain their old behaviour.

## Installation

Simply copy the contents of the GameData folder of this mod into your KSP installs GameData folder, or just use CKAN of course.

## Possible future additions

Next to compatibility with Mk2 Stockalike Expansion I am also looking at tweaking the Mk3 spaceplane parts, as they have similar, though not as extreme, issues with low fuel loading / high drag at reasonable angles of attack.

## License

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/legalcode).