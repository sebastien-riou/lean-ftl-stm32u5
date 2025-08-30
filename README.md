# lean-ftl-stm32u5
Testbench for [lean-ftl](https://github.com/sebastien-riou/lean-ftl) on STM32U5A5 Nucleo board.

## Dependencies

### Lean-ftl
Run the following to get leam-ftl release:

````
./get-lean-ftl
````

### Cortex-M33 Toolchain
This projected as been tested with https://github.com/xpack-dev-tools/arm-none-eabi-gcc-xpack/releases/tag/v14.2.1-1.1

## How to build and run using CLI
Build using make:

````
make -C minSizeRel clean all
````

Load using:

````
./flash
````

Expected result:

- The Green LED should shine for several seconds while all test execute.
- It shall blink at around 1 Hz if all tests passed.

If the green LED is blinking at around 5 Hz, an error occured.

## How to import in STM32CubeIDE
Import the top folder as "General -> Existing Projects into Workspace".

