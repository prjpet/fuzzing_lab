# fuzzing_lab
Notes for the lab exercise

First we are going to be working on the Ubuntu server (major version 20)

1. apt update / upgrade

2. apt install make, gcc, gdb

3. https://github.com/gynvael/stream-en
3.b Work in subfolder 017-fuzzing-basics
3.c analyse what is in there talk about it
3.d asdf.c is a simple application that takes an input file named input sample. gynvael made his own fuzzer in python, which is a mutational fuzzer that modifies the a certain number of bits, bytes or else. It's interesting if you want to write your own fuzzer, but I don't recommend it for production environments.

4. We are going to use Americal Fuzzy Lop as said earlier
4.b git clone https://github.com/mirrorer/afl
4.c analyse what is in there
4.d make

5. Compile asdf.c 2x with GCC / with afl-gcc

6. Copy the files over to Windows - On the server
6.c Copy the files to a new folder
6.d Rename them for their names to make sense (smg like afl_instrumented_example.out / not_instrumented_example.out)
6.f Change permissions as root to peter:peter recursively

7. Copy the files over to Windows - On the windows machine
7.b $credential = Get-Credential
7.c Get-SCPFolder -ComputerName '95.179.134.57' -Credential $credential -LocalFolder 'C:\Users\peter\Desktop\fuzzing_lab' -RemoteFolder '/home/peter/copy'
7.d Install IDA Freeware
7.c Open the compiled binary in IDA pro and note the differences

9. Fuzz! - On the server
9.b Create a new dir input/ in afl/
9.c Create a new dir output/ in afl/
9.d afl-fuzz -i i -o o4 -- ./a.out @@

10. Once a bug found, we will attempt to triage it.
10.b Run GDB with the non instrumented application: gdb a.out
10.c Try the different files that were found, discuss what we see: https://www.exploit-db.com/papers/13205

11. Get exploitable.py
11.b git clone https://github.com/jfoote/exploitable
11.c create python setup.py install
11.d instert into gdb as described on git

12.: BONUS:
https://github.com/philwantsfish/gdb_commands
https://github.com/longld/peda
