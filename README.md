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

| Instruction |   Opcode          |    |r, s, Q| Reg. |
|:-----------:|:-----------------:|:--:|:-----:|:----:|
| NOP         | ``00 000 000``    |    | B     | 000  |
| LD r, s     | ``01 rrr sss``    |    | C     | 001  |
| LD r, n     | ``00 rrr 110 n `` |   | H     | 100  |
| LD BC, nn   | ``00 010 000 n n``| | L     | 101  |
| LD HL, nn   | ``00 110 000 n n``| | A     | 111  |
| LD (HL), n  | ``00 110 110 n `` |   |       |      |
| LD (HL), r  | ``01 110 rrr``    |    |       |      |
| LD r, (HL)  | ``01 rrr 110``    |    |       |      |

| Instruction |   Opcode       | Hex |   | Instruction |   Opcode       | Hex |
|:-----------:|:--------------:|:---:|:-:|:-----------:|:--------------:|:---:|
| LD b, b     | ``01 000 000`` | 40  |   | LD a, h     | ``01 111 100`` | 7c  |
| LD b, c     | ``01 000 001`` | 41  |   | LD a, l     | ``01 111 101`` | 7d  |
| LD b, h     | ``01 000 100`` | 44  |   | LD a, a     | ``01 111 111`` | 7f  |
| LD b, l     | ``01 000 101`` | 45  |   | LD b, n     | ``00 000 110`` | 06 n|
| LD b, a     | ``01 000 111`` | 47  |   | LD c, n     | ``00 001 110`` | 0e n|
| LD c, b     | ``01 001 000`` | 48  |   | LD h, n     | ``00 100 110`` | 26 n|
| LD c, c     | ``01 001 001`` | 49  |   | LD l, n     | ``00 101 110`` | 2e n|   
| LD c, h     | ``01 001 100`` | 4c  |   | LD a, n     | ``00 111 110`` | 3e n|   
| LD c, l     | ``01 001 101`` | 4d  |   | LD BC, n n  | ``00 010 000`` | 20 n n|   
| LD c, a     | ``01 001 111`` | 4f  |   | LD HL, n n  | ``00 010 110`` | 26 n n|   
| LD h, b     | ``01 100 000`` | 60  |   | LD (HL), n  | ``00 110 000`` | 30 n|
| LD h, c     | ``01 100 001`` | 61  |   | LD (HL), B  | ``01 110 000`` | 70  |
| LD h, h     | ``01 100 100`` | 64  |   | LD (HL), C  | ``01 110 001`` | 71  |
| LD h, l     | ``01 100 101`` | 65  |   | LD (HL), H  | ``01 110 100`` | 74  |
| LD h, a     | ``01 100 111`` | 67  |   | LD (HL), L  | ``01 110 101`` | 75  |
| LD l, b     | ``01 101 000`` | 68  |   | LD (HL), A  | ``01 110 111`` | 77  |
| LD l, c     | ``01 101 001`` | 69  |   | LD b, (HL)  | ``01 000 110`` | 46  |   
| LD l, h     | ``01 101 100`` | 6c  |   | LD c, (HL)  | ``01 001 110`` | 4e  |
| LD l, l     | ``01 101 101`` | 6d  |   | LD h, (HL)  | ``01 100 110`` | 66  |
| LD l, a     | ``01 101 111`` | 6f  |   | LD l, (HL)  | ``01 101 110`` | 6e  |
| LD a, b     | ``01 111 000`` | 78  |   | LD a, (HL)  | ``01 111 110`` | 7e  |
| LD a, c     | ``01 111 001`` | 79  |   |             |                |     |

