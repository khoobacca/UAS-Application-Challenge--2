# UAS Application Challenge #2
 Takeoff Simulator

## Thoughts:

tbh I did a majority of the application last year when I applied, so I submitted that for the 24 hour window, and I want to take on this new challenge just to see what I can do. For now, I'll put my research here along with my thought process. Here goes nothing:

# Research

okay...

imma break thie problem into a couple steps. when i do research i normally break it up into a couple phases.
1.  concept introduction + basic notes
2. deeper investigation into necessary topics after general understanding/overview is finished.

another note is that when im researching and learning concepts, I look for applications immediately, and i also keep the learning at a very 'general' level. i mean i dont fixate on tiny details because I found that throws me off. If i see the bigger picture then Im able to break the problem down into more manageble chunks.

ill make sure that im using the given information:
- note: ill check it off once im finished using it
1. weight (done)
2. wingspan
3. wing area (done)
4. wing height above ground
5. fuselage frontal area
6. fusalage drag coefficient
7. overall vertical drage coefficient
8. wheel rolling resistance

anyways heres what I researched:

## Lift
lift (L) is the force opposing weight of the object and hold the aero-whatever we want int hte air.

Theres also these things called coefficient of lift (cL) and angle of attack (AoA). ill leave these alone for now.

I found the lift equation to be:

L = C * 1/2 * rho * V^2 * S

, which describes that lift is a function of wing shape, angle of attack, air density (rho), free stream velocity (V), and the surface area of the wing itself (S). Pretty self explanatory as is, but it turns out that the coefficient of lift (C), is a function itself of the wing shape and the angle of attack. The shape of wing shouldnt change shape mid flight, which means that we can assume this is constant, and the angle of attack is what affects the coefficient of lift.

if i rearrange the formula to get C i get:

C(AoA) = 2 * L / (rho * V^2 * S )

apparently people test their wings and stuff at this point in an air tunnel with this exact equation. kinda cool. ill prob use matlab and graph it out with your given values. if im understanding this correctly, since our changing variable (i forgot the formal name) is the angle of attack, we can graph the coefficient of lift as a function of angle of attack.

x_axis = AoA
y_axis = C

something like this and code the formula.

IN LAYMENS (for myself) : it is unitless quantity that compares lifting ability of wings at a given angle of attack. its specific for every wing design.

## Weight
Im assuming this is gravity lmao. i dont want to overcomplicate my process right now and for simplicity ill assume the following:
- even weight distribution

i guess thatsall im assuming so heres the formula:

F(g) = mg

## Drag
im going to initially assume that this is similar to the lift how it depends on angle of attack. i also know drag opposes thrust

after research, theres many types of drag:
- induced drag
- parasite drag
- form drag, skin friction drag, interference drag, and so on.

