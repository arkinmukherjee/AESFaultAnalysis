# AESFaultAnalysis
This code simulates a fault injection during AES and performs analysis to determine delta and the four key bytes used during encryption. 

To run the fault simulation and fault analysis, please run the "make" command in this directory. Once the code is compiled, you can use the "./testelf" to run the code. Doing so will print out in the terminal the fault analysis that was performed, including the delta value, the key values, and how much the fault space decreases by after more key bytes are guessed. 

All of the fault simulation and fault analysis was written in C, in the aes.c file. Within the Cipher function, the value of state[0][1] is XORed by the fault injection, which is set to 45. This only occurs in round 9 after ShiftRows and before MixColumns. The analysis is done in a function called faultAnalysis() in aes.c that is called in test.c.

