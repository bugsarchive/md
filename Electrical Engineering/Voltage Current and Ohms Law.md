% Current, Voltage, and Ohm's Law
% Rani

# Introduction

Ohm's law is one of the most ubiquitous equations in circuit analysis and
electrical engineering. It relates the current through a resistor to the voltage
across it using the "resistance," an inherent property of real conductors. In
order to understand Ohm's law, we need to first understand current and voltage.

## Current

Current (I) is defined as the "charge per unit time", `dQ/dt`, in units of
Amperes (A), which is Coulombs per Second in SI base units. Charge is an
inherent property of subatomic particles, notably the electron and proton. It is
important to note that while electrons are the primary energy carriers in a
circuit, current actually follows the opposite of the flow of the electrons --
if the electrons are moving up, current is defined as moving down. This is
because electrons have a negative charge, but current follows the (more
intuitive) flow of positive charges. However, electrons are set into motion by
means of voltage -- that is, current is typically not observed without a voltage
differential somewhere.

### Current Sources

Current is manifested through various circuit elements, but current sources
assert that an exact amount of current will always flow through them. Current
sources will assume the necessary voltage in order to drive the correct amount
of current. The following are circuit schematics for current sources:

```circuit
   o
   |
   |
 ( ^ ) N Amps          N Amps
 ( | )           o----( --> )----o
   |
   |
   o
```

An arrow indicates the direction of the current through the source, and the
label indicates the amount of current flowing through it.

Current sources are difficult to create in reality and may require relatively
complex circuits. However, they are very useful tools for generalizing circuits
or for creating equivalent circuits.

## Voltage

Voltage is, in effect, the "force" which causes charge carriers to move,
resulting in a current. It is defined formally as the electric field per unit
charge, though it is not necessary to know this for circuit analysis. Voltage
differentials are used instead to analyze circuits. For instance, a 9V battery
exposes a 9 Volt difference between its (+) and (-) terminals. While the actual
voltage of either terminal is likely unknown, it is only necessary to know the
difference between the two to analyze any circuit. Typically, the (-) terminal
is called the "ground," meaning it is a reference to 0V.

Voltage is the electrical analog to gravity. A charge carrier at high voltage
may want to follow an electric path (a wire or the like) until it reaches a
point of low voltage. Similarly, a ball on top of a hill has high gravitational
potential energy and may wish to roll until it reaches the bottom of the hill
where potential energy is lower. While it is relatively easy to determine the
exact gravitational potential energy of an object at a given point, the
calculation for work only needs to know the difference in potential in a manner
similar to voltage.

### Voltage Sources

Voltage sources provide a fixed voltage difference across them. They will push
out as much current as necessary in order to keep the voltage correct. The
following are circuit schematics for voltage sources:

```circuit
  o           o              o
  |           |              |
  |           |           _______ +
( + ) V    _______ +        ___                  V
( - )        ___     V    _______ V       o---( - + )---o
  |           |    -        ___
  |           |              |    -
  o           o              o
```

Voltage sources have (+) and (-) terminals, and a label beside them indicates
the voltage across the two terminals. A 9V source, for instance, will satisfy
the equation `V+ - V- = 9`, or there is a 9V difference between the voltage at
the (+) terminal and the voltage at the (-) terminal.

Voltage sources are commonly found in the form of batteries, power supplies, and
even the wall sockets in your home (though these provide a varying voltage
instead of a fixed one).

## Resistance

Real (physical) conductors are not perfect. While ideal conductors can carry an
infinite amount of current, real conductors are limited by their "Resistance".
Resistance is the property of a given conductor to "resist" the flow of current.
Resistance is defined in units of Ohms as `1/G`, the inverse of conductance.
Conductance measures how well a material conducts electricity.

A material with low resistance will allow a lot of current through, even if only
a small voltage is applied across it. This is typical of metals like silver or
copper. On the other hand, a material with high resistance will not allow as
much current through. A very long stretch of wire will eventually build up a
large amount of resistance, though insulators are inherently high resistance.
This is exemplary of materials such as rubber or air.

### Resistors

Resistors are devices with a known resistance. They are often used in circuits
for things like current limiting, current sensing, and more. They are very
versatile and ubiquitous circuit elements. The circuit schematic for a resistor
is as so:

```circuit
  o
  |
  |                R
 +-+        o---/\/\/\/---o
 | |
 | |  R
 +-+               R
  |             _______
  |        o---|_______|---o
  o
```

The blocky resistor model is typically referred to as IEC or "European" style,
while the zig-zaggy model is referred to as US or "American" style.

## Ohm's Law

Ohm's law is an equation defining the most important property of resistors:
their relation between current and voltage. A resistor with resistance R follows
the following relation: `V = IR`, where V is the voltage across it and I is the
current through it. This defines a linear relation between current and voltage,
and the IV curve (Current vs Voltage) can be plotted as such:

```graph
    I
    ^
    |    /
    |   /
    |  /
    | /
    |/
----+----------> V
   /|
  / |
```

From this graph we can see two things:

1. The slope is always equal to one over the resistance (`1/R`). Since the
   resistance is constant, we can say that resistors are linear circuit
   elements.

2. When the voltage across the resistor is 0, the current through it is also 0
   and vice versa. This is a property that is true for all resistors: there is
   no current without voltage, and there cannot be a voltage without current.

It is important to note that the IV curve of a resistor will always have a
positive slope. That means that increasing the magnitude of the voltage across a
resistor will always increase the magnitude of the current through it, and
decreasing the magnitude of the voltage will decrease the magnitude of the
current. This also means that the resistance of a resistor is always positive --
there is no such thing as a real negative resistor.

### Single Resistor Circuit Analysis

Let's try calculating the current and voltage for the resistors in the following
circuits:

```circuit
   +-----------+
   |           |
   |          +-+
 ( + ) 5V     | |
 ( - )        | |  5 Ohm
   |          +-+
   |           |
   +-----------+
```

In the circuit above, there is a 5 Ohm resistor connected across a 5 Volt
source.  To solve for the current and voltage, we can employ Ohm's law, `V =
IR`. In this case, the voltage across the resistor is already known. Since the
resistor is connected directly across the voltage source, the voltage across the
resistor is necessarily 5 Volts, the voltage across the voltage source. We also
know that the resistance, R, is 5 Ohms. This means that the only missing
variable is current, I. Rearranging, we find that `I = V/R`. Plugging in the
voltage and resistance gives that `I = 5/5 = 1A`. The current through the
resistor must then be 1 Ampere, or 1 Amp.

```circuit
   +------------+
   |            |
   |           +-+
 ( ^ ) 15A     | | 3 Ohm
 ( | )         | |
   |           +-+
   |            |
   +------------+
```

In this circuit, a 3 Ohm resistor is connected directly to a 15 Amp current
source. Since the current source is connected to the resistor and to nothing
else, it is fair to say that all the current that goes through the source will
also go through the resistor. Since we know that there is 15 Amps through a 3
Ohm resistor, we can calculate the missing variable, the voltage, by using Ohm's
law once more. In this case, we can use the equation without rearranging
anything. Ohm's law says that `V = IR`, so `V = (15)(3) = 45V`. So, we find that
the voltage across the resistor must be 45 Volts.

```circuit
   +-------------+
   |             |
   |            +-+
 ( + ) 25V      | |  | 5A
 ( - )          | |  V
   |            +-+
   |             |
   +-------------+
```

In the above circuit, a resistor is connected across a 25V voltage source and
it is noted that 5A of current is flowing through the resistor. However, the
resistance of the resistor is not given. We can once again solve for this
missing variable using Ohm's law. By rearranging, we find that `R = V/I`, so
`R = 25/5 = 5 Ohm`. Therefore, the resistor must be 5 Ohms in order to satisfy
the given circuit.

# Conclusion

By using Ohm's law, we can relate the current through a resistor and the voltage
across it using its resistance. We find that rearranging the equation will allow
for solving for different unknown variables in different situations. As long as
any two variables are known, the third is trivially calculated using Ohm's law.

While Ohm's law in this form only works for resistors, it can be later modified
to work with a variety of linear elements through what is called "Impedance."
Similar to resistance, it "impedes" the flow of current, though it is a more
complicated topic.

Note that most real materials have some resistance. While we model wires are
having no resistance, they still have some, although it is relatively small.
Superconductors are materials that have no resistance, but they are difficult
and expensive to create and maintain, so only regular conductors are used for
real world applications.
