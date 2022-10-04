# Aixt Project

The aim of this project is provide a tool for programing microcontrollers in a modern language but allowing compiling code even in low-resource devices. This project is composed by 3 main componentes:

- The **Aixt** programing language based on the [_V language_](https://vlang.io/) syntax.
- The **Aixt to C Transpiler**, which translate de **Aixt** source code to C, for the expecific C compiler of each microcontroller.
- The **Aixt API**, which makes the programming easy by standardizing the setup and I/O functions.  

## Aixt Language

**Aixt** programing language implements a subset of [_V language_](https://vlang.io/). The main difference is all of the variables in **Aixt** are mutable by default.

### Example with `main` function
```go
import machine { pin }

fn main() {

    pin(B0,OUT)     
    pin_high(B0)    //turn ON the PORTB0
}
```

### Example without `main` function
```go
/*blinking led example (XC16 compiler)
working on the PORTB pin 0 of a PIC24FJ microcontroller*/

import machine { pin }
import time { sleep_ms }

pin(B0,OUT)

for {   //infinite loop
    pin_high(B0)
    sleep_ms(500)
    pin_low(B0)
    sleep_ms(500)
}
```

## Aixt Transpiler

The transpiler is written in _Python_ using _SLY_ module as Lexer and Parser.

## Aixt API

The **Aixt API** is inspired on _Micropython_, _Arduino_ and _Tinygo_ projects.


#### Project's name
The project's name is inspired in _Veasel_ the Weasel pet of _V Language_, and as tribute to _Ticuna_ people who live in the Amazonic forest in the borders of _Colombia_, _Brasil_ and _Peru_. Weasels are _multelids_ like otters, so the name **Aixt** comes from _Aixtü_ word wich is a way to say otter in [_Ticuna_](https://www.sil.org/system/files/reapdata/90/20/51/90205190508691852389084667097660892450/tca_Ticuna_Dictionary_2016_web.pdf) language.