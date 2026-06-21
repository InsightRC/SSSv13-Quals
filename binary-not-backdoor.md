# Binary: Not Backdoor
Initially, given that it says not-backdoor.exe, I thought it was a PE file. I was wrong:

![back1](images/backdoor1.png)

I used 7z to extract the actual ELF and proceeded to further analyze.

![back2](images/backdoor2.png)

We can see the function XORs the flag. Went ahead and used cyberchef to bruteforce the key. It was 0x6f, that is 111: 

![back3](images/backdoor3.png)
