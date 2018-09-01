# mZ8
 Emulation of my own fantasy CPU mZ8
 
 mZ8 son las siglas de Mini Z8, una CPU inventada por mí que pretende ser una versión 
 reducida del Z80 de Zilog.
 
 Características:
 
 - CPU de 8 bits
 - Puede direccionar 65536 direcciones de memoria (64 KB)
 - Registros 8 bits: A, F, H, L, IX
 - Pueden combinarse A,F y H,L para formar el par AF, HL
 - Registros 16 bits: PC, SP

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

**Instrucciones de Carga**

| Instruction |   Opcode   |   |
|:-----------:|:----------:|---|
| NOP         | ``00 000 000`` |   
| LD r, s     | ``01 rrr sss`` |   
| LD r,n      | ``00 rrr 110`` |   
| LD R,nn     | ``00 RRR 000`` |   
| LD (HL), n  | ``00 110 110`` |   
| LD (HL), r  | ``01 110 rrr`` |   
| LD r, (HL)  | ``00 rrr 110`` |   

| Instruction |   Opcode       | Hex |   | Instruction |   Opcode       | Hex |   |
|-------------|----------------|-----|---|:-----------:|:--------------:|-----|---|
| LD b, b     | ``01 000 000`` | 40  |   | LD b, n     | ``00 000 110`` | 06  |   |
| LD b, h     | ``01 000 001`` | 41  |   | LD h, n     | ``00 001 110`` | 0e  |   |
| LD b, l     | ``01 000 010`` | 42  |   | LD l, n     | ``00 010 110`` | 16  |   |
| LD b, a     | ``01 000 011`` | 43  |   | LD a, n     | ``00 011 110`` | 1e  |   |
| LD h, b     | ``01 001 000`` | 48  |   | LD a, n     | ``00 011 110`` | 1e  |   |
| LD h, h     | ``01 001 001`` | 49  |   | LD a, n     | ``00 011 110`` | 1e  |   |
| LD h, l     | ``01 001 010`` | 4a  |   | LD a, n     | ``00 011 110`` | 1e  |   |
| LD h, a     | ``01 001 011`` | 4b  |   | LD a, n     | ``00 011 110`` | 1e  |   |
| LD l, b     | ``01 010 000`` | 50  |   | LD a, n     | ``00 011 110`` | 1e  |   |
| LD l, h     | ``01 010 001`` | 51  |   | LD a, n     | ``00 011 110`` | 1e  |   |
| LD l, l     | ``01 010 010`` | 52  |   | LD a, n     | ``00 011 110`` | 1e  |   |
| LD l, a     | ``01 010 011`` | 53  |   | LD a, n     | ``00 011 110`` | 1e  |   |
| LD a, b     | ``01 011 000`` | 58  |   | LD a, n     | ``00 011 110`` | 1e  |   |
| LD a, h     | ``01 011 001`` | 59  |   | LD a, n     | ``00 011 110`` | 1e  |   |
| LD a, l     | ``01 011 010`` | 5a  |   | LD a, n     | ``00 011 110`` | 1e  |   |
| LD a, a     | ``01 011 011`` | 5b  | - | LD a, n     | ``00 011 110`` | 1e  |   |

