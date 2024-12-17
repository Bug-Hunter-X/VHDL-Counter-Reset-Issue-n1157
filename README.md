# VHDL Counter Reset Bug

This repository demonstrates a common but subtle bug in VHDL code related to asynchronous reset handling in a simple counter. The bug lies in how the reset signal is handled within the clocked process. The original code only checks for the reset at the very start of the process. 

## Bug Description
The provided VHDL code implements a basic counter.  However, its handling of the reset signal is flawed. If the reset signal becomes high during the clock cycle, after the `if rst = '1'` condition has been checked, the counter will not reset correctly. 

## Solution
The solution employs synchronous reset handling. This ensures the reset signal is checked synchronously with the clock, preventing the issue by making sure the reset is checked at the proper moment.