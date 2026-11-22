# lean-ftl-stm32u5

> [!WARNING]
> **Deprecated.** This repository is no longer maintained. lean-ftl's test suite now runs on the
> NUCLEO-U5A5ZJ-Q as a [lean-bsp](https://github.com/sebastien-riou/lean-bsp) application:
> [lean-ftl](https://github.com/sebastien-riou/lean-ftl) built with
> [lean-bsp-nucleo-u5a5](https://github.com/sebastien-riou/lean-bsp-nucleo-u5a5), a board support package shared by every
> lean-bsp application, which holds the flash accessors the tests run with. Follow lean-ftl's
> `test/HWBRIDGE.md`, section "Run the test suite with lean-bsp" (on lean-ftl's `lean-bsp-app`
> branch until it is merged).
>
> That build compiles the library and the tests from source and prints the results
> (`Tests 1 to 45 PASSED`), where this testbench links a release's prebuilt libraries and only
> blinks the LED. This repository stays as it was, for reference.

## Instead: the lean-bsp build

With `lean-ftl` and `lean-bsp-nucleo-u5a5` cloned side by side, and lean-bsp and
[lean-hwbridge](https://github.com/sebastien-riou/lean-hwbridge) set up, from the `lean-ftl` directory:

````
lbsp build-load-run --bsp nucleo-u5a5 --until PASSED --timeout 600
````

The instructions below are this repository's own, kept as they were.

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

