# ECE 281 ICE 3: Ripple-Carry Adder with Top Level Design

This is a **template** repository.

[ICE 3 instructions](https://usafa-ece.github.io/ece281-book/ICE/ICE3.html)

Targeted toward Digilent Basys3. Make sure to install the [board files](https://github.com/Xilinx/XilinxBoardStore/tree/2018.2/boards/Digilent/basys3).

Tested on Vivado 2024.2

---

## GitHub Actions Testbench

The workflow uses the [setup-ghdl-ci](https://github.com/ghdl/setup-ghdl-ci) GitHub action
to run a *nightly* build of [GHDL](https://ghdl.github.io/ghdl/).

First, the workflow uses GHDL to **analyze** all `.vhd` files in `src/`.

Then it **elaborates** the entity defined by `$TB_ENTITY`

Finally, the workflow **runs** the simulation. If successful then it will quietly exit with a `0` code.
If any of the `assert` statements fail then GHDL will cease the simulation and exit with non-zero code; this will also cause the workflow to fail.
Assert statements of other severity levels will be reported, but not fail the workflow.

![This waveform shows the test cases in the test bench. The far left shows an input of 00, which is equal to 0000 + 0000, which produces the expected output of Cin = 0 and Cout = 0. There are four other test cases that produce their expected, respective outcomes](waveform.png)

![Input A is represented by switches 4 to 1, input B is represented by switches 15 to 12, Cin is represented by switch 0, the sum output is represented by leds 3 to 0, and Cout is represented by led 15](sketch.png)

## Documentation
I received help from C3C Jost and ChatGPT when it came to syntax errors in my VHDL. All code is original and AI only helped me debug.