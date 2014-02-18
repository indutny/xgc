# X GC

Experimental emulator (WIP, actually) of GC-enabled CPU. The architecture and
opcode design will be based on top of IA32 (though, I may also give a try to
ARM).

## Registers

* `p0` ... `p7` - special registers that could hold pointers
* `r0` ... `r7` - general purpose registers, that are suitable for arithmetics

## Instructions

* `alloc pX, %pcount, %wcount` - allocate chunk with `pcount` pointer slots and
  `wcount` data slots (each data slot occupies 8 bytes).
* `mov pX:[offset], %data` - store data inside memory chunk
* `mov %data, pX:[offset]` - load data from memory chunk
* `nil pX` - set register value to `nil`
* `isnil pX` - set flags according to comparison result
* ... other IA32 instructions ...
