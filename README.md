# fuzzing_lab
Notes for the lab exercises for the fuzzing lecture I give at the UvA

On the Ubuntu server

1. apt update / upgrade
2. apt install make, gcc, gdb, systemd-coredumpd


On the server

1. Copy the files to a new folder
2. Rename them for their names to make sense (smg like afl_instrumented_example.out / not_instrumented_example.out)
3. Change permissions as root to peter:peter recursively

On the Windows machine

$credential = Get-Credential

Get-SCPFolder -ComputerName $server_ip -Credential $credential -LocalFolder 'C:\Users\peter\Desktop\fuzzing_lab' -RemoteFolder '/home/peter/copy'
