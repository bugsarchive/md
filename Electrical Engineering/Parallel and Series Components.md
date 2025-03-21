% Parallel and Series Components
% Rani

# Introduction

When building a circuit, there are two ways to connect any two components:
series and parallel. When placing two components in either series or parallel,
they can be combined into a single component with a different resistance,
capacitance, or inductance (depending on the components being combined).

## Series Connections

When two components are in series, it is said that all current that flows
through one component will necessarily flow through the other component.
Elements that are connected in series will look like so:

```circuit
 o--+
    |
   +-+
   | |
   | | A
   +-+
    |
    |
   +-+
   | |
   | | B
   +-+
    |
    |
   +-+
   | |
   | | C
   +-+
    |
 o--+
```

It is clear that the current flowing through component A must also flow through
component B and all the current flowing through component B must also flow
through component C, since there is nowhere else for it to go. The number of
components that can be placed in series is arbitrary: you can place 2 components
in series, 73 components in series, or any other number. It remains true,
however, that the current through all the components is exactly equal.

## Parallel Connections

Two (or more) components in parallel will always have the same voltage across
them, but the current through each component is not necessarily equal. Elements
that are connected in parallel will look like so:

```circuit
 o-------+-------+-------+
         |       |       |
        +-+     +-+     +-+
        | |     | |     | |
        | | A   | | B   | | C
        +-+     +-+     +-+
         |       |       |
 o-------+-------+-------+
```

To understand why the voltage across all three elements must be the same, it can
be helpful to visualize a battery connected in parallel with the three
components (that is, placed across the open terminals). Since voltage sources
require that the voltage across them is constant and known, it is necessarily
true that the voltage across all three elements are also equal to the voltage
across the source. Although, this only makes sense when the polarity of all the
components is oriented in the same way (the (+) of all components connect to the
same wire (aka node) and the (-) terminals of all components connect to the same
node).

## Voltage Sources

When voltage sources are connected in series, the voltage across all the sources
is equal to the sum of all the individual voltages, keeping the polarities in
mind. This result is found by Kirchhoff's Voltage Law.

The following circuits are shown as an equivalent single voltage source:

```circuit
 o--+
    |
  ( + )           o--+
  ( - ) 5V           |
    |              ( + )
    |         =>   ( - ) 8V
  ( + )              |
  ( - ) 3V        o--+
    |
 o--+
```

In the above circuit, we find an equivalent by summing the voltages. Because the
two sources are oriented the same, we can add the voltages directly and know
that the equivalent will be oriented in the same way.

```circuit
 o--+             o--+
    |                |
  ( + )            ( + )         o--+
  ( - ) 5V         ( - ) 5V         |
    |                |            ( + )
    |        =>      |       =>   ( - ) 2V
  ( - )            ( + )            |
  ( + ) 3V         ( - ) -3V     o--+
    |                |
 o--+             o--+
```

In the above circuit, the polarities of the sources must be noted. Because the
3V source is facing the opposite direction of the 5V source, we can correct it
by flipping the polarity and negating the voltage. Now, since both sources are
facing the same way, we can add the voltages directly once again and copy the
polarity to get a 2V source. If the resulting equivalent source is negative, it
can be left as such, or the (+) and (-) terminals may be flipped and the voltage
turned positive. Both approaches are valid.

### Voltage Sources in Parallel

Because voltage sources force a set voltage across their two terminals, placing
two or more sources in parallel can have disastrous results, or it may do
nothing. If all the parallel sources have the same voltage, then the voltage
across all of them is still the same, and nothing happens. In the real world,
however, placing two batteries (of the same voltage) in parallel will allow
them to source more current, since each battery will have to source only half
the current.

If the voltage sources have different voltage, however, the results are
disastrous. When analyzing circuits, it is impossible for this situation to
2occur, and it referred to as an invalid circuit. In the real world, however,
this causes a short circuit. A high amount of current will be drawn, causing the
batteries and wires to heat up. For some batteries, this can cause them to catch
fire or explode. It is imperative to never connect batteries in this manner.

## Current Sources

When current sources are connected in parallel, the current out of all of them
is equal to the sum of the currents through the individual sources, keeping in
mind their directions. This result is found using Kirchhoff's Current Law.

The following circuits are shown as an equivalent single current source.

```circuit
 o-------+---------+            o---+
         |         |                |
       ( ^ )     ( ^ )            ( ^ )
       ( | ) 5A  ( | ) 3A   =>    ( | ) 8A
         |         |                |
 o-------+---------+            o---+
```

In the above case, because the current sources are pushing current in the same
direction, it is intuitive and fair to combine them into a single source pushing
the sum of the individual currents into the same direction.

```circuit
 o-------+---------+            o---+
         |         |                |
       ( ^ )     ( | )            ( ^ )
       ( | ) 5A  ( v ) 3A   =>    ( | ) 2A
         |         |                |
 o-------+---------+            o---+
```

In this case, the two sources are pushing current in opposite directions.
Because of this, the currents will instead subtract. Five amps going up minus
three amps going down gives two amps going up, so that will be the equivalent
source.

Note that while two sources can be combined into a single one, this loses
information about the current through the individual sources. While placing,
say, a resistor across the original circuit and equivalent circuit will cause it
to consume the same amount of power, assume the same voltage, and have the same
current passing through it, the equivalent source is really hiding two sources
inside of it.

### Current Sources in Series

Placing current sources in series will either do nothing, or lead to an invalid
circuit. This is very similar to what happens when placing voltage sources in
parallel. If two current sources with the same current flowing through them in
the same direction are placed in series, the result is the same as a single
current source with the same current as either of the two sources. However, if
the sources do not pass the same current, the circuit is invalid.

## Resistors

Resistors are modelled by their resistance, and connecting two resistors
together will appear as a single resistor with a different resistance.

### Series Resistors

Two resistors in series appear as a single resistor with the resistance equal to
the sum of the individual resistances.

```circuit
 o--+
    |
   +-+
   | | A =         o--+
   | | 5 Ohm          |
   +-+               +-+
    |                | | R =
    |          =>    | | 20 Ohm
   +-+               +-+
   | | B =            |
   | | 15 Ohm      o--+
   +-+
    |
 o--+
```

Series resistors with resistances `A, B, C, ...` are equivalent to a resistor
with resistance `R = A + B + C + ...`. This is because two resistors in series
is effectively the same as increasing the length of a resistor, which will cause
its resistance to increase.

### Parallel Resistors

Two resistors in parallel appear as a single resistor with a resistance that is
less than either resistor. The inverse of its resistance (1/R) will be equal to
the sum of the inverse of the resistances of the individual resistors.

```circuit
 o-------+----------+             o--+
         |          |                |
        +-+        +-+              +-+
        | | A =    | | B =    =>    | | R =
        | | 3 Ohm  | | 6 Ohm        | | 2 Ohm
        +-+        +-+              +-+
         |          |                |
 o-------+----------+             o--+
```

Parallel resistors with resistance `A, B, C, ...` are equivalent to a resistance
`1/R = 1/A + 1/B + 1/C + ...`. This will end up being less than any individual
resistance and can be thought of as increasing the area through which current
can flow, therefore decreasing resistance.

## Capacitors

Capacitors are modelled by their capacitance and connecting two capacitors will
appear as a single capacitor with a different capacitance.

### Series Capacitors

Connecting capacitors in series will appear as a single capacitor with decreased
capacitance. This is modelled by the same equation as that for parallel
resistors: series capacitors with capacitances `A, B, ...` are equivalent to
a capacitor with capacitance `1/C = 1/A + 1/B + ...`.

The result is initially unintuitive, but can be thought of as increasing the
distance between the plates of a capacitor, thereby decreasing its capacitance.

### Parallel Capacitors

Capacitors connected in parallel will appear as a single capacitor with
increased capacitance. In this case, the equivalent capacitance is equal to the
sum of all the individual capacitances. That is, parallel capacitors with
capacitances `A, B, ...` are equivalent to a capacitor with capacitance `C = A +
B + ...`.

Connecting capacitors in parallel effectively increases the area of the plates,
thereby increasing the capacitance.

## Inductors

Inductors are modelled by their inductance and behave similarly to resistors for
the purpose of series and parallel connections.

### Series Inductors

Much like resistors, series inductors with inductances `A, B, ...` are
equivalent to a single inductor with inductance `L = A + B + ...`. This is
because connecting inductors in series effectively increases the coil length,
increasing the inductance.

### Parallel Inductors

Parallel inductors with inductances `A, B, ...` are equivalent to a single
inductor with inductance `1/L = 1/A + 1/B + ...`.

## Mixing Components

It is easy to combine series and parallel components when they are the same type
of component. However, it is difficult to do this combination when circuits mix
resistors, capacitors, inductors, etc. together. Generally, it can be thought of
as impossible to combine two dissimilar components using the known rules for
parallel and series circuits without applying some complex transformation.

# Conclusion

Knowing the rules that apply to parallel and series circuits and the rules for
combining elements together helps to make many circuits much easier to solve.
Note, however, that two arbitrary elements in a circuit are not necessarily
series nor parallel connections, and so the equivalent element rules cannot
always be applied.  

Mixed circuits can actually be combined into much simpler ones by using phasors,
the Fourier transform, or the Laplace transform.  Resistors, capacitors, and
inductors may be combined with the rules of resistors when they are transformed
into impedance black-boxes. That is, modelling the components using a single
impedance instead of using resistance, capacitance, and inductance. Once this is
done, current and voltage sources can be combined by applying Thevenin's and
Norton's theorems. Then, any linear circuit can be modelled as a single
(complex) source with a single (complex) impedance.
