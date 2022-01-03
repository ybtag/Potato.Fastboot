# SharpBoot (Potato.Fastboot Fork)


NOTICE: Builds fail on tarvis ci since i have insufficent credits (migrate to git workflow wen)


![GPL-3.0](https://img.shields.io/github/license/mashed-potatoes/Potato.Fastboot.svg)

A small wrapper over LibUsbDotNet for easy and convenient communication with mobile devices in Fastboot mode.


## Examples

```csharp
var fastboot = new Fastboot();
fastboot.Connect();
Console.WriteLine("Connected.");
Console.WriteLine("Executing: fastboot reboot-fastboot"); 
fastboot.Reboot(Fastboot.RebootOptions.Fastbootd); // this reboots your phone into the userspace fastboot
```

```csharp
var fastboot = new Fastboot();
fastboot.Connect();
Console.WriteLine("Connected.");
Console.WriteLine("Executing: fastboot reboot-recovery"); // reboots your phone into recovery mode
fastboot.Reboot(Fastboot.RebootOptions.Recovery);
Console.WriteLine("Your device should be in Recovery Mode.");
```
  
```csharp
var fastboot = new Fastboot();
fastboot.Connect();
Console.WriteLine("Connected.");
fastboot.SendOemCommand("unlock"); // this sends the oem command unlock to the phone to then prompt if the bootloader should be unlocked
```
        
```csharp
var fastboot = new Fastboot();
fastboot.Connect();
Console.WriteLine("Connected.");
fastboot.Boot("//temp/boot.img"); // this sends the boot.img and boots it
```
```csharp
var fastboot = new Fastboot();
fastboot.Connect();
Console.WriteLine("Connected.");
fastboot.Flash("//temp/system.img","system_a"); // this sends the system.img and and flashes it to the partition: system_a
```
        
```csharp
var fastboot = new Fastboot();
fastboot.Connect();
Console.WriteLine("Connected.");
fastboot.ResumeBoot(); // this is the equivalent of fastboot continue
```

# License

[GNU General Public License v3.0](LICENSE.txt)

