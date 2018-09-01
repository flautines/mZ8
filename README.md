# mZ8
 Emulation of my own fantasy CPU mZ8
 
 mZ8 son las siglas de Mini Z8, una CPU inventada por mí que pretende ser una versión 
 reducida del Z80 de Zilog.
 
 Características:
 
 *CPU de 8 bits
 Puede direccionar 65536 direcciones de memoria (64 KB)
 Registros 8 bits: A, F, H, L, IX
 Pueden combinarse A,F y H,L para formar el par AF, HL
 
 Registros 16 bits: PC, SP
 ---------------------------
 **Instrucciones:**
    
|Mnemonic| Instruction               |
|----:|------------------------------|
| NOP | No Operation                 |
|  LD | Load                         |
| SBC | Substract with Carry         |
| ADC | Add with Carry               |
|  CP | Compare                      |
| AND | Bitwise AND with Accumulator |
| OR  | Bitwise OR                   |
| XOR | Bitwise XOR                  |
| SRA | Shift Right Arithmetic       |
| SLA | Shift Left Arithmetic        |
| SRL | Shift Right Logic            |
| SLL | Shift Left Logic             |
--------------------------- 
**Instrucciones de Carga**

| Instruction |   Opcode   |   |
|:-----------:|:----------:|---|
| NOP         | ``00 000 000`` |   |
| LD r, s     | ``01 rrr sss`` |   |
| LD r,n      | ``00 rrr 110`` |   |
| LD R,nn     | ``00 RRR 000`` |   |
| LD (HL), n  | ``00 110 110`` |   |
| LD (HL), r  | ``01 110 rrr`` |   |
| LD r, (HL)  | ``00 rrr 110`` |   |
