---
share: true
---
# Memory Hierarchy
![[Pasted image 20240331233136.png|Pasted image 20240331233136.png]]

---
# How Information is processed 

This is one layout we all are very familiar with. It’s the most basic of the computer layout which sacrifices some details for ease of understanding.

![[Pasted image 20240331234528.png|Pasted image 20240331234528.png]]

The flow of data comes as an input from devices and goes straight into memory, which is represented by Storage Unit. Here is where most of the confusion related to how memory is used and what's all inside starts. Let's take a look into it.

1. Primary Storage 
2. Secondary Storage

In computing, a device that is used to store information for immediate use in a computer or related computer hardware device is commonly called as memory. It typically refers to semiconductor memory where data is stored within metal–oxide–semiconductor (MOS) memory cells on a silicon integrated circuit chip. 

The term “memory” is often a colloquial short-hand with the term “primary storage”. Secondary storage or memory is often called “storage”.

The two “memories” of the processor, which are housed inside the ==Central Processing Unit (CPU)== are Registers and Cache. Though they are kind-of memories, but generally studied out of the memory system. These are the most expensive, and fastest memory access to the CPU. Let us have a look at them first.

---
# The memory of the CPU
## Registers 

Registers are the small storage locations used by the CPU to store data and instructions. They are built into the processor itself. Hence these memory locations can be accessed by the processor directly. This makes them the fastest accessible memory. Registers are measured by the number of bits they can hold, for example, an “8-bit register”, “32-bit register” or a “64-bit register”. 32-bit and 64-bit are commonly used to describe processor architecture or processor design. A 32-bit processor has a 32-bit register, which can store 232 or 4,294,967,296 values. A 64-bit processor has a 64-bit register, which can store 264 or 18,446,744,073,709,551,616 values.

If you ever wondered, while installing software, what is the difference between the 32-bit and 64-bit versions, now you know.
## Cache Memory

Cache memory is not an _original_ memory, but a copy of some parts of “Main Memory” which is used frequently. Hence cache is a smaller, faster memory, located closer to a processor core, which stores copies of the data from frequently used main memory. When trying to read from or write to a location in the main memory, the processor first checks whether the data from that location is already in the cache. If so, the processor will read from or write to the cache instead of the much slower main memory. This helps to reduce the average cost (time or energy) to access data from the main memory.

The small memories which are closer to the CPU can operate faster than the much larger main memory. Most CPUs since the 1980s have used one or more type of caches.

When trying to read from or write to a location in the main memory, the processor checks whether the data from that location is already in the cache. If so, the processor will read from or write to the cache instead of the much slower main memory.

Many modern desktop, server, and industrial CPUs have at least three independent caches:

1. Instruction cache (I-cache)
    Used to speed executable instruction fetch
2. Data cache (D-cache)
    Used to speed data fetch and store; the data cache is usually organized as a hierarchy of more cache levels (L1, L2, etc.; see also multi-level caches below).
3. Translation lookaside buffer (TLB)
    Used to speed virtual-to-physical address translation for both executable instructions and data. A single TLB can be provided for access to both instructions and data, or a separate Instruction TLB (ITLB) and data TLB (DTLB) can be provided. However, the TLB cache is part of the memory management unit (MMU) and not directly related to the CPU caches.

---
# Primary Memory (a.k.a main memory, internal memory, or prime memory)

_Primary storage_, often referred to simply as _memory_, is the only one directly accessible to the CPU. The CPU continuously reads instructions stored there and executes them as required. Any data actively operated on is also stored therein in a uniform manner.

This one diagram details it all. The two kinds of Primary Memory are ROM and RAM.
![[Pasted image 20240401010325.png|Pasted image 20240401010325.png]]
**ROM**: Read Only Memory

**RAM**: Random Access Memory

RAM and ROM are very popular abbreviations, which every student knows from middle school, but I can say for myself, that I was always confused about how they differ in form and functionality. And when I connected the dots, I was excited. Because the new things I learned about them were all about known things, which were never perceived like what they are. So I am trying to make you connect those dots yourself.

Everyone knows that ROM is a read-only memory. But Why? Where is this Memory Housed? What functions does it perform?
## Read-Only Memory (ROM)

![[Pasted image 20240401011234.png|Pasted image 20240401011234.png]]
[^^] _Opened ROM cartridge for the Game Boy Color. _

This is a type of _non-volatile memory_ used in computers and other electronic devices. Non Volatile means that no power is needed to keep the memory alive. The data stored in ROM **cannot** be electronically modified after the manufacture of the memory device.

Now almost every device comes with Factory Reset. Hence I will use this analogy to make understanding ROM easier for you.

The memory of your computer, which is built-in into it, when the computer is being manufactured/assembled in the factory, is the ROM. Data Stored in ROM is not alterable, non-modifiable easily. Hence, that software that is rarely changed during the life of the computer system is stored in a ROM memory device. This kind of software is also known as _Firmware_. (Firmware is a very common term, and computer or such systems reset to it when factory reset applied. )

Hence, think of it as the ==most basic== and ==most important== memory. Basic because, you can **_only READ_** it, but **_can’t WRITE_** anything on it. This memory space is not open to the user. The *BIOS* of your computer is one such example. 

Another example can be Video Games Cartridges, which are plug and play. They store the Game in ROM. Many game consoles use interchangeable ROM cartridges, allowing for one system to play multiple games. ROM comes before the Operating System. ==And it allows the computer to have its own Firmware.==

_Everything else comes after that,_ ==_even the Operating system._==
## Mask ROM

![[4go8ave1.bmp|4go8ave1.bmp]]
[^^] _Samsung KM23C4000P-15 4M-Bit (512Kx8) CMOS MASK ROM 32Pin P DIP OMA037D_

The first ROM was hard-wired. They were made up of electronic components such as _[[Diodes|Diodes]]_ or _[[Integrated Circuits (ICs)|Integrated Circuits (ICs)]]_, which ==_cannot_ be altered after manufacture==. These ROM ICs are also called Mask ROM Integrated Circuits. Thereafter, if there is any upgradation in ROM to be made, it _has_ to be replaced. A new ROM with new upgraded firmware can be installed, but the old ROM and the firmware **_cannot be changed._** (Hard wired, Remember… )

In the Mask ROM IC, data is hard encoded, physically, during the manufacturing. So it can be programmed only during the fabrication. This creates many hurdles:

1. Because each Mask ROM is programmed during manufacturing, its cost becomes very high, since users must contract with a foundry to produce a custom design. It is only possible to order it in large quantities.

2. Getting a ROM manufactured is time taking process, as each ROM is customized.

3. For R&D use, where the users have to do trial and error or modify and improve the contents in the memory for refining a design, Mask ROM becomes impractical.

4. If ROM is faulty, and the product is shipped, it can’t be corrected without Total Recall.
## Programmable ROM (PROM)

![[qqlqjh58.bmp|qqlqjh58.bmp]]
[^^] _Texas Instruments PROM type TBP18SA030N._

These shortcomings created a need for Programmable ROM (PROM). These were invented by Wen Tsing Chow in 1956, allowed users to program its contents exactly once by physically altering its structure with the application of high-voltage pulses. This addressed problems 1 and 2 above since a company can simply order a large batch of fresh PROM chips and program them with the desired contents at its designers’ convenience. However, this was also possible one time only.
## Erasable Programmable ROM (EPROM)

![[e8mod6kz.bmp|e8mod6kz.bmp]]
[^^] _Erasable programmable read-only memory (EPROM) integrated circuits in dual in-line packages. These packages have a transparent window that shows the die inside. The window is used to erase the memory by exposing the chip to ultraviolet light._

In 1971, Dov Frohman of _Intel_ invented Erasable Programmable Read-Only Memory (EPROM). This new ROM, known as EPROM essentially solved the 3rd hurdle in the list above, since EPROM (unlike PROM) can be repeatedly reset to its un-programmed state by exposure to strong ultraviolet light. 
It’s worth noting that it was still ==nearly impossible for a user to erase the ROM _(Which is exactly as intended)_==, and rewrite it. It only solved problems for well-equipped labs and R&D centers.

![[4tjrzt56.bmp|4tjrzt56.bmp]]
[^^] _The first EPROM, an Intel 1702, with the die and wire bonds clearly visible through the erase window._
## Electrically Erasable Programmable ROM (EEPROM)

![[bqsqovcm.bmp|bqsqovcm.bmp]]
[^^] _STMicro M24C02 I²C serial type EEPROM_

EEPROM was developed by Yasuo Tarui, Yutaka Hayashi, and Kiyoko Naga at the Electrotechnical Laboratory in 1972. This could be ==programmed even at a remote location== _(using just a computer and serial cable)._ This helped the computing industry cross the 4th hurdle as well. Now faulty ROM could be reprogrammed at the consumer’s or user’s place, without the need of taking the entire device back to the manufacturer.
## Flash Memory

![[zblw8qdg.bmp|zblw8qdg.bmp]]
[^^] _A disassembled USB flash drive. The chip on the left is flash memory. The controller is on the right._

Going forward, Fujio Masuoka at Toshiba invented Flash Memory in the early 1980s and commercialized it in the late 1980s. ==Flash Memory is a form of EEPROM==. This uses the chip area _very efficiently_ and can be erased, programmed, and reprogrammed _thousands of times_ ==without any damage==.

But it’s one groundbreaking advancement was that ==now any specific part of the device could be erased==. _(Earlier ROMs needed to be deleted in totality)_. This can be done at high speed, hence the name “flash”.

After the advent of Flash Memories as ROMs, the entire ROM scenario has changed from “One-time Programmable” to “Regular Updating of ROM”. ==The best example of the same is regular updates of the firmware of various computer systems.== Earlier, the firmware was not easy to change or upgrade. Now in mobile devices, companies push remote upgrades of the firmware, and the user downloads and updates the same.
## Why do we still have EPROM and Mask ROM?

A natural question comes to mind, that after all the advantages of EEPROM, why do we still have the old and less functional types of ROMs?

The answer is simple. **_COST._**

All the advanced technologies increased the flexibility of the ROM chip, but there is a downside of it as well. The technology comes at a very high cost per chip. And many systems do not need ROM to upgrade for their life, making the additional cost burden unnecessary. Hence, as long as the large quantity MASK ROMs are cheaper (economy of scale), they will remain the ROM of choice for many devices for years.

---
# Random Access Memory (RAM)

![[bgnkvtly.bmp|bgnkvtly.bmp]]
[^^] _Example of writable volatile random-access memory: Synchronous Dynamic RAM modules, primarily used as main memory in personal computers, workstations, and servers._

**Random Access Memory** is the _Volatile Memory_ of the computer. It means, ==it forgets whatever was stored inside it as soon as the power is switched off==. RAM is an expensive “memory real estate” and hence in normal computing devices, it varies from 512 MB to 8 GB _(Some expensive devices, both PC and Mobile have much higher RAM as well)_. 
More amount of RAM is associated with the faster working of the computer. The reason for it can be understood if we understand how a computer manages its internal memory for operation _(only Volatile one, not ROM)_.

RAM is essentially super-fast, high-speed storage that the computer and its applications utilize to store and access temporary data. ==It can be thought of like a computer’s short-term memory==. When a program starts _(for example Google chrome browser or Microsoft Excel file)_, its common data is stored on RAM, and as RAM is much faster than a hard drive _(Secondary Memory)_, the program runs faster by having data directly accessible from RAM. As soon as the program ends (you close the browser or file), the RAM gets free from its data. Hence, the larger the RAM, the faster the computer works with more number of simultaneous programs.

Computers with lesser RAM can't do many things at once. Say for example you are working on multiple video files, and at the same time, open many web browsers. The RAM requirement goes up with each new program being opened. What happens when the amount of “Temporary Memory” requirement of a computer exceeds the RAM? Modern computers use a memory management technique called Virtual Memory.

![[Pasted image 20240401151020.png|Pasted image 20240401151020.png]]
[^^] _Virtual memory combines active RAM and inactive memory on DASD[a] to form a large range of contiguous addresses._

This is a method to expand the RAM capacity. A portion of the computer’s hard drive is set aside for a paging file, and now the sum total of the RAM and Paging file becomes the total “Temporary Memory”. However, there is a catch. ==The hard drive is **much** slower than the RAM==. And every time the computer relies on to take data from the paging file from the hard drive, it gets a slower response than the RAM would offer.

Hence, the higher the RAM, the faster the computer operations become.

Now the natural question arises again. Why the RAM is in the range of 1 to 8 GB (or at times somewhat higher) but the hard drives are in range of 512 GBs to 2 TBs _(1 Terabyte = 1024 GB)_?
## When RAM is so important, why not have higher RAM?

The answer is again, the **_COST_**.

The ==two main types of volatile random-access memory are **Static random-access memory (SRAM)** and **Dynamic random-access memory (DRAM)**==. Commercial uses of semiconductor RAM date back to 1965, when IBM introduced the SP95 SRAM chip for their System/360 Model 95 computer, and Toshiba used DRAM memory cells for its Toscal BC-1411 electronic calculator.
## Static random-access memory (SRAM)

In Static RAM, data is stored in a six-transistor (one kind of semiconductor) memory cell which requires a constant flow of power. 
Because the power flow is constant, it doesn’t need _refreshing_ the memory to remember the data being stored. This is called static because there is no change needed ( no refreshing needed) to keep the data intact. It is used in cache memory.

This requires lesser power and gives faster access and speed. But at the same time, it’s less dense in memory (lesser memory in the same size) and hence has a higher cost.
## Dynamic random-access memory (DRAM).

In Dynamic RAM, data is stored in transistor and capacitors (Made of metal and not a semiconductor) pair memory cell. Capacitors discharge energy slowly. And hence data (which is stored in form of energy) is also lost. Therefore a periodic refresh of power is required to keep it functioning. DRAM is called dynamic as it needs a constant change of power (refreshing) to keep the data intact.

This requires higher power consumption and has slower access to data as compared to SRAM. But at the same time, it’s denser in memory (more memory in the same size) and hence has a lower cost.

Many computer systems have a memory hierarchy consisting of processor registers, on-die SRAM caches, external caches, DRAM, paging systems, and virtual memory on a hard drive. This entire pool of memory may be referred to as “RAM”.

---
# Secondary Memory (also known as external memory or auxiliary storage):

Secondary storage (also known as external memory or auxiliary storage) is different from primary storage because it is not directly accessible by the CPU. The computer uses its input/output channels to access secondary storage and transfer the desired data to primary storage. Secondary storage is non-volatile (data is retained even when power is switched off).

![[re7avbjg.bmp|re7avbjg.bmp]]
[^^] _Image with various types of storage medias._

The access time per byte for HDDs or SSDs is typically measured in milliseconds (one-thousandth seconds), while the access time per byte for primary storage is measured in nanoseconds (one billionth seconds). Thus, secondary storage is significantly slower than primary storage.

Check [[Different types of media storages|Different types of media storages]]