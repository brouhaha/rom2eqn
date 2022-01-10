# rom2eqn - convert a ROM to logic equations

Hosted at the
[rom2eqn Github repository](https://github.com/brouhaha/rom2eqn/).

## Introduction

ROMs are sometimes used to implement logic functions. The rom2eqn program,
written in Python 3, can convert a ROM binary image to logic equations in
VHDL.

rom2eqn uses a Python implementation of the Quine McCluskey logic
minimization algorithm by Thomas Pircher. The necessary file is included,
but the upstream project is at https://github.com/tpircher/quine-mccluskey

## Usage

Supposing that you have a binary file containing a 1Kx4 ROM image, named
341-0061.bin, you can use the command:

    rom2eqn -a 10 -d 4 -l cupl 341-0061.bin

to generate logic equations with generic signal names of inputs, A0 through A9,
and outputs, D0 through D3, and write the equations in CUPL syntax to standard
output.

A definitions file can be used to name the signal. The defintion file contains
a series of lines, each of which has one default signal name (e.g. A3 or D2),
whitespace, and a replacement symbol name (e.g., PA15 or PRAS4_5). Lines starting
with a "#" are comments.

If the definitions file name is 341-0061.def, then the command to generate the
equations is:

    rom2eqn -a 10 -d 4 -l cupl -d 341-0061.def 341-0061.bin

## rom2eqn license

rom2eqn is free software: you can redistribute it and/or modify it
under the terms of version 3 of the GNU General Public License as
published by the Free Software Foundation.

This program is distributed in the hope that it will be useful, but
WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU
General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see http://www.gnu.org/licenses/.

## qm.py license

qm is covered by the MIT license. See the license statement at the
top of the qm.py source file.


