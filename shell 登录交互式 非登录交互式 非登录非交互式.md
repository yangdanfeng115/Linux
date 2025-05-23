测试前：
写入到~/.bashrc
echo ">> ~/.bashrc loaded at $(date)" >> /tmp/bashrc.log

写入到/etc/profile
echo ">> /etc/profile loaded at $(date)" >> /tmp/profile.log

root@slurmd2:/# cat /tmp/profile.log

>> /etc/profile loaded at Fri May 23 06:14:03 UTC 2025
>> 
>> /etc/profile loaded at Fri May 23 06:40:35 UTC 2025
>> 
>> /etc/profile loaded at Fri May 23 06:40:58 UTC 2025
>> 
>> /etc/profile loaded at Fri May 23 06:42:34 UTC 2025
>> 
root@slurmd2:/# cat /tmp/bashrc.log

>> ~/.bashrc loaded at Fri May 23 06:14:18 UTC 2025
>> 
>> ~/.bashrc loaded at Fri May 23 06:40:35 UTC 2025
>> 
>> ~/.bashrc loaded at Fri May 23 06:40:58 UTC 2025
>> 
>> ~/.bashrc loaded at Fri May 23 06:41:46 UTC 2025
>> 
>> ~/.bashrc loaded at Fri May 23 06:42:15 UTC 2025
>> 
>> ~/.bashrc loaded at Fri May 23 06:42:34 UTC 2025
>> 
root@slurmd2:/# bash -l  （登录交互式 经过/etc/profile ~/.bashrc）

root@slurmd2:/# cat /tmp/profile.log

>> /etc/profile loaded at Fri May 23 06:14:03 UTC 2025
>> 
>> /etc/profile loaded at Fri May 23 06:40:35 UTC 2025
>> 
>> /etc/profile loaded at Fri May 23 06:40:58 UTC 2025
>> 
>> /etc/profile loaded at Fri May 23 06:42:34 UTC 2025
>> 
>> /etc/profile loaded at Fri May 23 06:43:22 UTC 2025
>> 
root@slurmd2:/# cat /tmp/bashrc.log

>> ~/.bashrc loaded at Fri May 23 06:14:18 UTC 2025
>> 
>> ~/.bashrc loaded at Fri May 23 06:40:35 UTC 2025
>> 
>> ~/.bashrc loaded at Fri May 23 06:40:58 UTC 2025
>> 
>> ~/.bashrc loaded at Fri May 23 06:41:46 UTC 2025
>> 
>> ~/.bashrc loaded at Fri May 23 06:42:15 UTC 2025
>> 
>> ~/.bashrc loaded at Fri May 23 06:42:34 UTC 2025
>> 
>> ~/.bashrc loaded at Fri May 23 06:43:22 UTC 2025
>> 
root@slurmd2:/# exit
logout
root@slurmd2:/# bash （非登录交互式 ~/.bashrc）
root@slurmd2:/# cat /tmp/profile.log

>> /etc/profile loaded at Fri May 23 06:14:03 UTC 2025
>> 
>> /etc/profile loaded at Fri May 23 06:40:35 UTC 2025
>> 
>> /etc/profile loaded at Fri May 23 06:40:58 UTC 2025
>> 
>> /etc/profile loaded at Fri May 23 06:42:34 UTC 2025
>> 
>> /etc/profile loaded at Fri May 23 06:43:22 UTC 2025
>> 
root@slurmd2:/# cat /tmp/bashrc.log

>> ~/.bashrc loaded at Fri May 23 06:14:18 UTC 2025
>> 
>> ~/.bashrc loaded at Fri May 23 06:40:35 UTC 2025
>> 
>> ~/.bashrc loaded at Fri May 23 06:40:58 UTC 2025
>> 
>> ~/.bashrc loaded at Fri May 23 06:41:46 UTC 2025
>> 
>> ~/.bashrc loaded at Fri May 23 06:42:15 UTC 2025
>> 
>> ~/.bashrc loaded at Fri May 23 06:42:34 UTC 2025
>> 
>> ~/.bashrc loaded at Fri May 23 06:43:22 UTC 2025
>> 
>> ~/.bashrc loaded at Fri May 23 06:43:58 UTC 2025
>> 
root@slurmd2:/# exit
exit
root@slurmd2:/# bash -c 'hostname' （非登录非交互式 一个都不经过）

slurmd2
root@slurmd2:/# cat /tmp/profile.log

>> /etc/profile loaded at Fri May 23 06:14:03 UTC 2025
>> 
>> /etc/profile loaded at Fri May 23 06:40:35 UTC 2025
>> 
>> /etc/profile loaded at Fri May 23 06:40:58 UTC 2025
>> 
>> /etc/profile loaded at Fri May 23 06:42:34 UTC 2025
>> 
>> /etc/profile loaded at Fri May 23 06:43:22 UTC 2025
>> 
root@slurmd2:/# cat /tmp/bashrc.log

>> ~/.bashrc loaded at Fri May 23 06:14:18 UTC 2025
>> 
>> ~/.bashrc loaded at Fri May 23 06:40:35 UTC 2025
>> 
>> ~/.bashrc loaded at Fri May 23 06:40:58 UTC 2025
>> 
>> ~/.bashrc loaded at Fri May 23 06:41:46 UTC 2025
>> 
>> ~/.bashrc loaded at Fri May 23 06:42:15 UTC 2025
>> 
>> ~/.bashrc loaded at Fri May 23 06:42:34 UTC 2025
>> 
>> ~/.bashrc loaded at Fri May 23 06:43:22 UTC 2025
>> 
>> ~/.bashrc loaded at Fri May 23 06:43:58 UTC 2025
>> 
root@slurmd2:/# exit

exit

root@trx:/home/ydf# 
