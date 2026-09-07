## The intelligence your mother warned you about

The evolution beyond the four-bit wonder.

This project advances the Four-Bit Wonder from an operator-controlled memory
experiment into a machine that acts toward a specified result. In the original
machine, the operator selects an address, enters a four-bit value, and controls
reading and writing. The person supplies the decisions.

In **phase one**, the operator supplies a target between 0 and 15, and the
circuitry handles the decisions: read the value at the selected SRAM address,
compare it with the captured target, increase or decrease it by one, and write
it back. The machine repeats this loop until the values match, then halts.
A target latch, comparator, up/down counter, and slow sequencer make this a
visible hardware hill climber, with LEDs indicating increase, decrease, and
match/halt. Manual operation remains available. See the
[phase-one bill of materials](phase-one/phase-one-bom.md).

In **phase two**, the machine also selects successive addresses automatically.
Starting at address zero, it brings each stored value to the target before
advancing to the next address. This extends autonomy from changing one value
to repeating the task across all 64 memory locations exposed by the panel.
The core design uses one captured target for every address; optional phase 2B
would add a separate target for each address, with its programming method
still to be decided. See the [phase-two plan](phase-two/phase-two-bom.md).

The advance is in **control and autonomy**, rather than numerical capacity.
The machine still works with four-bit values, but gains comparison,
sequencing, corrective action, and a stopping condition. It demonstrates a
building block of goal-directed behaviour through a fixed feedback loop; it
does not yet learn rules, choose its own goals, or run general-purpose programs.
Its SRAM working state is volatile and is not reliably retained without power.

The current [Machine Autonomous Version](phase-two/machine-autonomous-version.md)
combines the manual base machine and both phases on a new Vector `8016-1`
wire-wrap board, leaving the original Four-Bit Wonder intact. The
[incremental addition to the original board](phase-one/four-bit-wonder-autonomous-addition.md)
is retained as a separate legacy design. These documents describe the planned
design and parts allocations; they do not establish that either phase has been
built and tested.
