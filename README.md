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

| Instruction |   Opcode       |    |r, s, Q| Reg. |
|:-----------:|:--------------:|:--:|:-----:|:----:|
| NOP         | ``00 000 000`` |    | B     | 000  |
| LD r, s     | ``01 rrr sss`` |    | C     | 001  |
| LD r,n      | ``00 rrr 110`` |    | H     | 100  |
| LD R,nn     | ``00 RRR 000`` |    | L     | 101  |
| LD (HL), nn | ``00 110 110`` |    | A     | 111  |
| LD (HL), r  | ``01 110 rrr`` |    |       |      |
| LD r, (HL)  | ``00 rrr 110`` |    |       |      |

| Instruction |   Opcode       | Hex |   | Instruction |   Opcode       | Hex |
|:-----------:|:--------------:|:---:|:-:|:-----------:|:--------------:|:---:|
| LD b, b     | ``01 000 000`` | 40  |   | LD l, c     | ``01 101 001`` | 69  |
| LD b, c     | ``01 000 001`` | 41  |   | LD l, h     | ``01 101 100`` | 6c  |
| LD b, h     | ``01 000 100`` | 44  |   | LD l, l     | ``01 101 101`` | 6d  |
| LD b, l     | ``01 000 101`` | 45  |   | LD l, a     | ``01 101 111`` | 6f  |
| LD b, a     | ``01 000 111`` | 47  |   | LD a, b     | ``01 111 000`` | 78  |
| LD c, b     | ``01 001 000`` | 48  |   | LD a, c     | ``01 111 001`` | 79  |
| LD c, c     | ``01 001 001`` | 49  |   | LD a, h     | ``01 111 100`` | 7c  |
| LD c, h     | ``01 001 100`` | 4c  |   | LD a, l     | ``01 111 101`` | 7d  |
| LD c, l     | ``01 001 101`` | 4d  |   | LD a, a     | ``01 111 111`` | 7f  |
| LD c, a     | ``01 001 111`` | 4f  |   | LD b, n     | ``00 000 110`` | 06  |
| LD h, b     | ``01 100 000`` | 60  |   | LD c, n     | ``00 001 110`` | 0e  |
| LD h, c     | ``01 100 001`` | 61  |   | LD h, n     | ``00 100 110`` | 26  |
| LD h, h     | ``01 100 100`` | 64  |   | LD l, n     | ``00 101 110`` | 2e  |   
| LD h, l     | ``01 100 101`` | 65  |   | LD a, n     | ``00 111 110`` | 3e  |   
| LD h, a     | ``01 100 111`` | 67  |   | LD c, n     | ``00 000 110`` | 1e  |   
| LD l, b     | ``01 101 000`` | 68  |   | LD c, n     | ``00 000 110`` | 1e  |   

