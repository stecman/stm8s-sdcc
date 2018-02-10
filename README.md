# STM8S for SDCC

This is a slightly modified version of the [STM8S/A Standard
peripheral library](http://www.st.com/en/embedded-software/stsw-stm8069.html) that supports the [SDCC compiler](http://sdcc.sourceforge.net/).

The code from ST doesn't support SDCC out of the box, and on Linux there don't appear to be any other supported compiler options for the STM8 architecture.

## Usage

Include `inc/stm8s.h`. This contains all of the preprocessor logic for different device types and includes other driver headers as needed.

Add a define to your compiler flags to select your device:

| Device def | Family name |
|------------|-------------|
| `STM8S208` | STM8S High density devices with CAN |
| `STM8S207` | STM8S High density devices without CAN |
| `STM8S007` | STM8S Value Line High density devices |
| `STM8AF52Ax` | STM8A High density devices with CAN |
| `STM8AF62Ax` | STM8A High density devices without CAN |
| `STM8S105` | STM8S Medium density devices |
| `STM8S005` | STM8S Value Line Medium density devices |
| `STM8AF626x` | STM8A Medium density devices |
| `STM8AF622x` | STM8A Low density devices |
| `STM8S103` | STM8S Low density devices |
| `STM8S003` | STM8S Value Line Low density devices |
| `STM8S903` | STM8S Low density devices |

### Register-only mode

Define `NO_STDPERIPH_DRIVER` if you only care about using the registers defined in this library and none of the C functions.

Note that this causes enums from peripheral headers to also be excluded currently (eg. `TIM4_PRESCALER_256`).

## Licence

Copyright © 2015 STMicroelectronics International N.V.. All rights reserved.

Redistribution and use in source and binary forms, with or without modification, are permitted, provided that the following conditions are met:

1.  Redistribution of source code must retain the above copyright notice, this list of conditions and the following disclaimer.
2.  Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.
3.  Neither the name of STMicroelectronics nor the names of other contributors to this software may be used to endorse or promote products derived from this software without specific written permission.
4.  This software, including modifications and/or derivative works of this software, must execute solely and exclusively on microcontroller or microprocessor devices manufactured by or for STMicroelectronics.
5.  Redistribution and use of this software other than as permitted under this license is void and will automatically terminate your rights under this license.

THIS SOFTWARE IS PROVIDED BY STMICROELECTRONICS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS, IMPLIED OR STATUTORY WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NON-INFRINGEMENT OF THIRD PARTY INTELLECTUAL PROPERTY RIGHTS ARE DISCLAIMED TO THE FULLEST EXTENT PERMITTED BY LAW. IN NO EVENT SHALL STMICROELECTRONICS OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.