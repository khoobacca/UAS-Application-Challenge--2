# Takeoff Simulator

DISCLAIMER: I found several better programs to test flight. This program is a flop :)
I stsarted usign XFLR5 and XFOIL instead.

# Research

okay...

imma break this problem into a couple steps. when i do research i normally break it up into a couple phases.
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

> L = C * 1/2 * rho * V^2 * S

, which describes that lift is a function of wing shape, angle of attack, air density (rho), free stream velocity (V), and the surface area of the wing itself (S). Pretty self explanatory as is, but it turns out that the coefficient of lift (C), is a function itself of the wing shape and the angle of attack. The shape of wing shouldnt change shape mid flight, which means that we can assume this is constant, and the angle of attack is what affects the coefficient of lift.

if i rearrange the formula to get C i get:

> C(AoA) = 2 * L / (rho * V^2 * S )

apparently people test their wings and stuff at this point in an air tunnel with this exact equation. kinda cool. ill prob use matlab and graph it out with your given values. if im understanding this correctly, since our changing variable (i forgot the formal name) is the angle of attack, we can graph the coefficient of lift as a function of angle of attack.

> x_axis = AoA
> y_axis = C

something like this and code the formula.

IN LAYMENS (for myself) : it is unitless quantity that compares lifting ability of wings at a given angle of attack. its specific for every wing design.

i just did more research and i found this equation. it should be more helpful:
> cL = lift_slope * AoA + cL(0)

the cL(0) is the coefficient of lift at takeoff which is easy to calculate bc ig you can assume that lift force = weight at that point in time.

## Weight
Im assuming this is gravity lmao. i dont want to overcomplicate my process right now and for simplicity ill assume the following:
- even weight distribution

i guess thatsall im assuming so heres the formula:

> F(g) = mg

i can graph weight due to 

## Drag
im going to initially assume that this is similar to the lift how it depends on angle of attack. i also know drag opposes thrust

after research, theres many types of drag:
- induced drag
- parasite drag
- form drag, skin friction drag, interference drag, and so on.

I found this equation for 'hydrodynamic force' which is fancy for the actual force of drag. cD is the coefficient of drag, and im using the variable C here.

> D = C * 1/2 * rho * u^2 * A

this can be rearranged (like the lift equation), to calculate the drag coefficient:

> C = 2 * D / (rho * u^2 * A)

with this equation, i can now calculate drag for different object sizes going different velocities. (rho) in this case is fluid density, which for us is air, (u) is flow speed, and A is the surface area of the object that we're analyzing.

i can graph drag force due to velocity.

### research on drag coefficient, oswald, and k???
did more research and i found another equation:
> cD = cD(0) * cL(0) * constant???????

the cL(0) is the coefficient of lift at takeoff. it builds off eachother. scary. cD(0) is drag at takeoff, and its being multiplied by some constant k????

okay... the k factor seems to be this thing relate to an aspect ratio???????

heres an equation i found:

> k = 1/(pi * e * aspect_ratio)

this aspect ratio is simple. its the square of the wingspan over the wing area.

> aspect_ratio = wingspan^2 / wing_area

DAMN turns out e isnt really e. its another thing called the oswald efficiency factor. bruh. imma do more research.

after even more research, apparently its some sort of efficiency factor. it accounts for non ideal behaviour and apparently e is normally 0.7-1 for most subsonic aircraft wings. 1 is most ideal, so for my values ill use the least ideal lmao. e for me is now gonna be 0.7

## Thrust
this is opposite to drag. its the force that makes the whatever we want go anywhere we want. thrust happens because we're accelerating matter behind it. newtons 3rd law. heres the equation:

> T = v (dm/dt)

basically something like a plane has to accelerate hot air and fuel with enough force to accelerate the plane itself forward.

if im right we can graph thrust force (which will help overcome drag and gravity) due to velocity.


# update
scratch everything about what i said about graphing up above, heres what makes more sense:

1. graph and model to drag and lift coefficients due to the angle of attack
2. graph the thrust AND drag due to velocity

note: idk what to do about weight... ill just graph the mass to weight ratios of the substances i provided in challengem #1.b
note: AoA at 4.5m/s was 6deg as an instantaneous change, so ill model everything based on this.

# the questions:
1. A list of information you used and their sources (e.g. formulas, code blocks, etc.)

> see everything above haha

2. The maximum speed the airplane can go

> max speed is when drag = thrust
> takeoff: thrust > drag, bc we need it to accelerate
> drag increases as it speeds up until it reaches a speed where the drag overtakes the thrust

3. The horizontal speed at which vertical forces balance (ignoring vertical speed)
4. A graph showing the acceleration of the aircraft over time
5. A graph showing the velocity of the aircraft over time
6. A graph showing the takeoff trajectory of the airplane
7. The minimum runway length for takeoff
8. Factor in ground effect into the takeoff roll and redo graphs for 4 - 7
