## Communication protocol:

Wireless communication - Bluetooth HC-06 module.

Data transfered via serial port to the ATMEGA-328p (ARDUINO Uno).

- Baud rate = 9 600,
- Data bits = 8 bits,
- Parity = None,
- Stop bit = Yes

### Message bytes:

SYNC     = 0x55,
LENGTH   = 0x01 - 0xFF,
STOP     = 0x00,
ROTATE   = 0x0A,
RUN      = 0x0B,
ESC      = 0xAA,
ESC SYNC = 0x01

ROTATE VALUE (2B) = Turn right  > 0 > Turn Left
RUN VALUE (2B)    = Run Forward > 0 > Run Backward

### Message examples:

- Stop: SYNC, LENGTH (0x01), STOP
- Turn: SYNC, LENGTH (=0x03), ROTATE, ROTATE VALUE (2B)
- Go:   SYNC, LENGTH (=0x03), RUN, RUN VALUE (2B)
