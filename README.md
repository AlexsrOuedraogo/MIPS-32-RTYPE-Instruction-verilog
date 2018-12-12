# MIPS-32-RTYPE-Instruction-verilog
This is simple a MIPS32 RTYPE instruction using verilog

The memory output is a 32 bit signal containing instruction.

The 6 last bit [31:26] are sending to the controle unit in the case of Rtype 
instruction ---- [000000] the controle unit return trhee signal High : 
_registerwrite to active the writing of register who is pointing by  the instruction 
[15:11](rd). 
_AluCont to active the AluControle.
_RegisterDst to put the mux who indicate the registerwrite valu on rd.

Then the register recive three 5 bit signal rt,rs,rd respectivly [25:21][20:16][15:11] of Instruction
 this three signal get in three decoder5_32 
A register is a kind of memory who contain a 4 8 or in this case 32 bit(integer) value MIPS 32 contain 32 register

 exemple : The decoder 1 recieve form intruction[25:21] the value [000110] 
		and return [00000000000000000000000000000000000000000001000] the fourth pin is connected
		to the fourth register  so the fourth register output the value he contain to the ALU input A.
		same process for the second register and intruction[20:16].

The Alu  :receive as input 3 signal the first is the value retruning by the regiter pointed by intruction[25:21]
		the second is the value retruning by the regiter pointed by intruction[20:16]
		the third is the select value 3 bit signal . so where is caming the third signal ? 

From the Alu controle : who have as input function corresponding to intruction[5:0].
			The Alu control when recieve the high signal of the control returning the thirst
			3 bit of  intruction[5:0].

The Alu contain adder subb ect and have as input the valu given by register bloc and Alu controle.
He doing all operation at the same time and the outputting is selectect by a three to 8 bit decoder who
each bin is conected to one operation 32 bit out put wiht a gate and.
and we get the result. 

 
