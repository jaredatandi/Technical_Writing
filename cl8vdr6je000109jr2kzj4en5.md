## Root User Cool Tweaks

As a root user in Linux, you have access to all of the operating system's files and settings. This gives you the ability to make any changes you want, no matter how small or large.

One of the most common things root users do is install new software. With access to the entire file system, you can add or remove any programs you want. This is especially useful for installing programs that aren't available in the default repositories.

If you're a power user, you might also want to tweak some of the more advanced settings in Linux. For example, you can change the kernel parameters to optimize performance or enable new features. You can also modify the system configuration files to customize the behavior of programs and daemons.

Of course, with great power comes great responsibility. Making changes to the system as root can have unintended consequences, so it's important to be careful when making any modifications. Always have a backup plan in case something goes wrong.

With a little bit of experience, tweaking Linux as root can be a fun and rewarding experience. Just be sure to exercise caution, and you'll be fine.

Here are some of the things you can do.

- Change the swappiness value: This setting controls how often the kernel swaps memory pages to disk. A higher value means that the kernel will swap more often, while a lower value means that the kernel will swap less often. It can be beneficial in scenarios such as improving system performance or reducing power consumption. You can change the swappiness value by using the following command:

```
$ echo 0 > /proc/sys/vm/swappiness
 ```

 - Change the scheduler: The Linux kernel comes with a few different schedulers. The scheduler value is used by the Linux kernel to determine how to best schedule processes for optimal performance. If a process is not scheduled optimally, it can lead to poor performance. Changing the scheduler value as root can help ensure that processes are scheduled optimally. You can change which scheduler is used by the kernel by using the following command:

 ```
 $ echo noop > /sys/block/sda/queue/scheduler
 ```

 - Change the I/O scheduler: The I/O scheduler controls how the kernel schedules disk I/O requests. The I/O scheduler value can be changed as root in order to improve system performance. Changing the I/O scheduler can help to improve the responsiveness of the system, as well as increase throughput. You can change the I/O scheduler by using the following command:

 ```
 $ echo deadline > /sys/block/sda/queue/scheduler
 ```

 - Change the readahead value: The readahead value controls how much data the kernel reads from the disk when it anticipates heavy workloads such as accessing large files.

 ```
 $ echo 128 > /sys/block/sda/queue/read_ahead_kb
 ```

 - Change the system hostname: The hostname is the name that is used to identify your machine on a network. Changing it can help to ensure that communications are not confused or disrupted. Additionally, some applications may require that the hostname be changed in order to function properly. You can change it by running the following command:

 ```
 $ hostname new_hostname
 ```

 - Change the system timezone. The system timezone value should be changed as root in order to ensure that the system time is accurate. If the system time is inaccurate, it can cause problems with applications and services that rely on the system time.

 The timezone is the part of the world that your system is in. This can be changed by running the following command:

 ```
 $ timedatectl set-timezone new_timezone
 ```

 - Install new software: As a root user, you have the ability to install new software on your system. This can be done using a package manager such as apt or yum. Use the following command incase you are using apt

 ```
 $ apt install software-name
 ```

 - Create new user accounts: If you need to add a new user to your system, you can do so by running the following command:

 ```
 $ useradd new_user
 ```

 - Change file permissions: You can use the `chmod permission-value filename` command to change the permissions of a file. This can be useful if you need to create executable files.

 - Change the ownership of files and directories: You can use the `chown` command to change the ownership of any file or directory on the system. This can be useful if you need to give another user access to a certain file or folder.

 - Create and delete users: The `useradd` and `userdel` commands can be used to create and delete users, respectively. This can be useful if you need to add or remove a user from the system for any reason.

 - Create and delete groups: The `groupadd` and `groupdel` commands can be used to create and delete groups, respectively. This can be useful for managing access to certain files or resources on the system.

 - Install updates and security patches. Keeping your system up-to-date is one of the best ways to protect it from vulnerabilities.

 - Configure firewalls. A firewall can help protect your system from malicious activity.

 - Enable encryption. Encrypting your data can help protect it from being accessed by unauthorized parties.

 - Set up user accounts. Creating user accounts can help you control who has access to your system and what they can do.

 These are just a few of the tweaks you can perform as a root user in Linux. By taking advantage of the features and tools available to you, you can make your system more secure and efficient.