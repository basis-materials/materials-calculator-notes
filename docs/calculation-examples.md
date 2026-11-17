# Calculation examples

## 1. Atomic fraction and mass fraction

For element `i`:

- `x_i` is its atomic fraction: its atom count divided by the total atom count.
- `w_i` is its mass fraction: its mass divided by the total elemental mass.
- `M_i` is its elemental molar mass in `g/mol`, using a consistent set of atomic-weight values.

The conversion equations are:

```text
w_i = (x_i * M_i) / sum_j(x_j * M_j)
x_i = (w_i / M_i) / sum_j(w_j / M_j)
```

Divide percentage inputs by 100 before using these fraction equations. Multiply the resulting fractions by 100 to report percentages.

First check that the input percentages total 100%. If they do not, correct the inputs or explicitly choose to normalize them. When normalization is intentional, replace each fraction `p_i` by `p_i / sum_j(p_j)` and record that choice. Do not silently treat an incomplete or inconsistent composition as a complete recipe.

For a theoretical batch mass `m_total`:

```text
m_i = m_total * w_i
```

## 2. Equiatomic Cu-Ni: fixed illustrative constants

Assume 50 at% Cu and 50 at% Ni, with the following specified constants for this hand-worked example:

| Element | Atomic fraction | Molar mass used (g/mol) |
| --- | ---: | ---: |
| Cu | 0.5 | 63.546 |
| Ni | 0.5 | 58.6934 |

The denominator is:

```text
0.5 * 63.546 + 0.5 * 58.6934 = 61.1197 g/mol
```

Therefore:

```text
w_Cu = 31.773 / 61.1197 = 0.519848755802139...
w_Ni = 29.3467 / 61.1197 = 0.480151244197861...
```

| Element | at% | wt% | Theoretical mass in a 100 g batch (g) |
| --- | ---: | ---: | ---: |
| Cu | 50 | 51.984876 | 51.984876 |
| Ni | 50 | 48.015124 | 48.015124 |
| Total | 100 | 100.000000 | 100.000000 |

The table rounds only the displayed results to six decimal places. Substituting the unrounded mass fractions into the inverse equation recovers atomic fractions of 0.5 and 0.5.

Try the composition in the [Alloy Composition Calculator](https://basismaterials.com/pages/alloy-composition-calculator). The live tool uses its stated atomic-weight table, whose abridged values may differ from the fixed constants above; a small numerical difference should be checked against the constants used.

This is a synthetic calculation example, with no stock or product-availability claim. The batch masses assume pure elemental contributions and omit process losses, volatilization and impurities.

## 3. Thin-film mass with explicit units

Assume a single uniform film over a total coated area of `100 cm^2`, with thickness `100 nm` and assumed density `8.96 g/cm^3`.

```text
1 nm = 10^-7 cm
100 nm = 10^-5 cm = 0.00001 cm

Film volume = area * thickness
            = 100 cm^2 * 0.00001 cm
            = 0.001 cm^3

Film mass = volume * density
          = 0.001 cm^3 * 8.96 g/cm^3
          = 0.00896 g
          = 8.96 mg
```

Compare the same inputs in the [Thin Film Material Calculator](https://basismaterials.com/pages/thin-film-material-calculator). The area here already includes every coated face; do not apply another substrate-count or coated-sides multiplier to the same area.

Using bulk density is an approximation: an actual deposited film may have a different density. This mass is the deposited film mass. It does not predict source-material consumption, minimum crucible charge, sputtering-target lifetime or deposition rate.
