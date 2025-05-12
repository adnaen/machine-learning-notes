# Positional Encoding

- In all Languages words order is important.
- We know that in transformer architecture there is text process in parallel, not in sequentially (recurrently).
- So that, it cannot find the token position correctly. Thats were `Positional Encoding` coming.

## How it work?
- It uses Sinusoidal method
- for even idx position it use sin, for odd it use cos

