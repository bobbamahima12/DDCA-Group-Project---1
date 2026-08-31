# 8-Bit Signed Binary – Sign-Magnitude Representation

## Project Overview

This project demonstrates the implementation of **8-bit signed binary numbers using the Sign-Magnitude representation method**.

The circuit is designed and simulated using **Logisim**. It separates the sign bit from the magnitude bits and demonstrates how a signed value is interpreted.

## Problem Statement

Standard unsigned binary representation cannot represent negative numbers. In Sign-Magnitude representation, the first bit (MSB) is used as the sign bit and the remaining seven bits represent the magnitude.

- `0` → Positive
- `1` → Negative
- Remaining 7 bits → Magnitude

### Example

| Binary Input | Sign | Magnitude | Decimal Value |
|---|---:|---:|---:|
| `00000101` | 0 | 5 | +5 |
| `10000101` | 1 | 5 | -5 |
| `00000000` | 0 | 0 | +0 |
| `10000000` | 1 | 0 | -0 |

## Representation

```text
+---------+-----------------+
| Sign Bit|    Magnitude    |
|   1 bit |      7 bits     |
+---------+-----------------+
|   B7    |     B6 ... B0   |
+---------+-----------------+
```

For 8-bit Sign-Magnitude representation, the range is **-127 to +127**. There are two representations of zero: `00000000` (+0) and `10000000` (-0).

## Design and Methodology

The implementation follows these stages:

1. **Input Decoding** – An 8-bit input is divided into 1 sign bit and 7 magnitude bits.
2. **Sign Logic** – The MSB determines whether the number is positive or negative.
3. **Magnitude Processing** – The lower seven bits represent the absolute value.
4. **Output** – The separated sign and magnitude are made available for observation and validation.

## Logisim Circuit

The supplied `.circ` file demonstrates the core sign-magnitude decoding:

```text
B7 → Sign
B6..B0 → Magnitude
```

A labeled input bus, splitter, sign output, and magnitude output are provided.

## Test Cases

| Input | Expected Value |
|---|---:|
| `00000000` | +0 |
| `10000000` | -0 |
| `00000001` | +1 |
| `10000001` | -1 |
| `00000101` | +5 |
| `10000101` | -5 |
| `01111111` | +127 |
| `11111111` | -127 |

### Example Walkthrough

For `10000101`:

- MSB = `1` → negative
- Magnitude = `0000101`
- `0000101₂ = 5₁₀`
- Therefore, the value is **-5**

## Advantages

- Easy to understand.
- Sign can be determined directly from the MSB.
- Positive and negative values have a symmetric range.
- Magnitude is directly available from the lower seven bits.

## Limitations

- There are two representations of zero.
- Addition and subtraction require different logic depending on the signs.
- More sign-handling logic is required than in Two's Complement.
- Sign-Magnitude is less commonly used for modern integer arithmetic.

## Repository Structure

```text
8-bit-sign-magnitude/
├── README.md
├── circuit/
│   └── 8_bit_sign_magnitude.circ
├── documentation/
│   └── Project_Report.pdf
├── presentation/
│   └── Presentation.pdf
└── test-cases/
    └── test_cases.txt
```

## How to Run

1. Open the `.circ` file in Logisim.
2. Use the 8 input switches to enter an 8-bit binary number.
3. Observe the sign output and magnitude output.
4. Compare the result with the supplied test cases.

## Learning Outcomes

- Understanding signed binary representation.
- Understanding Sign-Magnitude encoding.
- Separating sign and magnitude using digital logic.
- Designing and testing circuits in Logisim.
- Documenting a digital logic project.

## Team Members

- M Hiteshram – 2620030066
- Kevin – 2620030078
- M. Haasini – 2620030081
- Mahima – 2620030076

## Project Information

**Project:** 8-Bit Signed Binary – Sign-Magnitude Representation  
**Domain:** Digital Logic / Computer Architecture  
**Simulation Tool:** Logisim
