# Demystifying Containers - Part I: Kernel Space

## Knowledge Check Questions

1.  **True or False:** Containers are best understood as lightweight virtual machines.

2.  **True or False:**  `chroot` is a mechanism in UNIX-like operating systems used to change the apparent root directory for a process.

3.  **True or False:**  The `chroot` mechanism is considered a completely secure and robust method for containerization in modern systems.

4.  For modern container runtimes, what system call is typically used instead of `chroot` for changing the root filesystem?

* A) `clone()`
* B) `unshare()`
* C) `pivot_root()`
* D) `setns()`

5.  What is a key component needed for a more functional "jail" environment, containing binaries and libraries?

* A) hypervisor
* B) virtual network interface
* C) root filesystem (rootfs)
* D) control group

6.  **Multiple Choice:** Containers are best defined as:

* A) Virtual machines with shared kernels.
* B) Isolated groups of processes.
* C) Hardware virtualization instances.
* D) Emulated operating systems.

7.  **True or False:** Containers, by definition, are designed to operate within the confines of a single host operating system kernel.

8.  **Select all that apply:** Which of the following are types of Linux namespaces important to containers? (Select all that apply)

* A) CPU (cpu) namespace
* B) Mount (mnt) namespace
* C) Network (net) namespace
* D) User (user) namespace
* E) Memory (mem) namespace

9.  What is the primary purpose of the PID namespace?

* A) To isolate network interfaces.
* B) To isolate process identifiers (PIDs).
* C) To isolate user and group IDs.
* D) To isolate filesystem mount points.

10. What is the primary purpose of the UTS namespace?

* A) To isolate network interfaces.
* B) To isolate hostname and domain name.
* C) To isolate inter-process communication.
* D) To isolate user and group IDs.

11. What is the primary purpose of the IPC namespace?

* A) To isolate inter-process communication (IP- C) resources.
* B) To isolate process identifiers (PIDs).
* C) To isolate user and group IDs.
* D) To isolate filesystem mount points.

12. What is the purpose of the Mount (mnt) namespace?

* A) To isolate network interfaces.
* B) To isolate process IDs.
* C) To isolate user and group IDs.
* D) To isolate filesystem mount points.

13. What is the purpose of Control Groups (cgroups) in the context of containers?

 * A) To provide network isolation.
 * B) To manage and limit resource usage.
 * C) To isolate user and group IDs.
 * D) To change the root directory.
     
14.  **Fill in the blank:** The  ___________ mechanism is of fundamental importance for container technology as it provides the core isolation that defines containers.