# rop-obf-Crackmes.one
Writeup to the Crackme Rop-obf from Crackmes.one
![File : rop-obf ](https://github.com/sandrabeme/rop-obf-Crackmes.one-/tree/master/images/file.png)

A stripped binary but looking inside you see its just a couple of push statements. On further exploring you see the stack cointains a couple of instructions which is actualy be pushed initially by assembly instuctions which eventually gets executed eventually.

![stack being pushed with instucrions which are executed later on!](https://github.com/sandrabeme/rop-obf-Crackmes.one-/tree/master/images/stack.png)

Finally, after the exit block is executed(according to gdb) , after a couple of instructions are executed you see the Scanf being called immediately followed by a getchar call  which .

With the obtained information I played a little with different inputs whiched helped me with figuring out that the binary takes 6 integers and a character alternatively.

![The compare statements](https://github.com/sandrabeme/rop-obf-Crackmes.one-/tree/master/images/rop.png)

On further analysis(Dynamically on gdb) figured out a cmp satetement which directly compares the value of the input integers with a hardcoded value after manipulation. 

### Operations on Input Made Before Comparison:

* inp1^0x83
* inp2^0x36
* inp3^0x9d
* inp4^0xcd
* inp5^0xec
* inp6^0xf6

Check the value against which the output is check for the required input. 

