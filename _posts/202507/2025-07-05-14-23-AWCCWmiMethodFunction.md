---
title: AWCCWmiMethodFunction
date: 2025-07-05 14:23:00+0800
categories: ["Software"]
tags: ["AWCC", "WMI", "ACPI"]
author: <admin> 
---

Two things have been done recently.

## The 1st thing.

I have been using this tool [alienfx-tools](https://github.com/T-Troll/alienfx-tools) as an alternative to AWCC for a long time.

But this software cannot customize marco keys, in my situation, I cannot use the 5 macro keys (`Fn + F2-F6`, i.e, `A-E`) on my Dell G17 7630.

So I did a search, and found this repo, [Alien-Macros](https://github.com/mscreations/Alien-Macros).

However, I cannot use tool direcetly, because,

1. This tool only tested on the author's Alienware m17 R4.
2. This repo hasn't been updated for more than a year, I'm not sure whether it will be updated later.
   
So I write a tool for my own G16 7630 based on this repo.

I also put my tool on the github: [AlienMacroKeys](https://github.com/StoolMonster/AlienMacroKeys).

## The 2nd thing.

I'm also interested in how [alienfx-tools](https://github.com/T-Troll/alienfx-tools) can replace AWCC in some way (not all, f.e., the macro keys), so I read the source code and did some test.

Go to the installing foler of alienfx-tools, run powershell as admin, and run,

```shell
alienfan-cli.exe dump
```

This line accesses the mof info of the WMI class `AWCCWmiMethodFunction` through WMI.

On my laptop, this command returns

```shell
AlienFan-CLI v9.3.0.1
Supported hardware (67109378) detected, 2 fans, 12 sensors, 5 power states, G-Mode, TCC, XMP.
Names:
[WMI, dynamic: ToInstance, provider("WmiProv"), Locale("MS\\0x409"), Description("WMI Function"), guid("{A70591CE-A997-11DA-B012-B622A1EF5492}")]
class AWCCWmiMethodFunction
{
    [key, read] string InstanceName;
    [read] boolean Active;
    [WmiMethodId(13), Implemented, read, write, Description("Return Overclocking Report.")] void Return_OverclockingReport([out] uint32 argr);
    [WmiMethodId(14), Implemented, read, write, Description("Set OCUIBIOS Control.")] void Set_OCUIBIOSControl([in] uint32 arg2, [out] uint32 argr);
    [WmiMethodId(15), Implemented, read, write, Description("Clear OC FailSafe Flag.")] void Clear_OCFailSafeFlag([out] uint32 argr);
    [WmiMethodId(19), Implemented, read, write, Description("Get Fan Sensors.")] void GetFanSensors([in] uint32 arg2, [out] uint32 argr);
    [WmiMethodId(20), Implemented, read, write, Description("Thermal Information.")] void Thermal_Information([in] uint32 arg2, [out] uint32 argr);
    [WmiMethodId(21), Implemented, read, write, Description("Thermal Control.")] void Thermal_Control([in] uint32 arg2, [out] uint32 argr);
    [WmiMethodId(22), Implemented, read, write, Description("BIOS OC Control.")] void BIOSOCControl([in] uint32 arg2, [out] uint32 argr);
    [WmiMethodId(23), Implemented, read, write, Description("MemoryOCControl.")] void MemoryOCControl([in] uint32 arg2, [out] uint32 argr);
    [WmiMethodId(24), Implemented, read, write, Description("AmdRyzenPlatformOCControl.")] void AmdRyzenPlatformOCControl([in] uint32 arg2, [out] uint32 argr);
    [WmiMethodId(25), Implemented, read, write, Description("OC Default Value.")] void OCDefaultValue([in] uint32 arg2, [out] uint32 argr);
    [WmiMethodId(26), Implemented, read, write, Description("System Information.")] void SystemInformation([in] uint32 arg2, [out] uint32 argr);
    [WmiMethodId(27), Implemented, read, write, Description("Bios OC Knobs.")] void BiosOCKnobs([in] uint32 arg2, [out] uint32 argr);
    [WmiMethodId(28), Implemented, read, write, Description("Power Information.")] void PowerInformation([in] uint32 arg2, [out] uint32 argr);
    [WmiMethodId(30), Implemented, read, write, Description("TCC Control.")] void TccControl([in] uint32 arg2, [out] uint32 argr);
    [WmiMethodId(32), Implemented, read, write, Description("FW Update GPIO toggle.")] void FWUpdateGPIOtoggle([in] uint32 arg2, [out] uint32 argr);
    [WmiMethodId(33), Implemented, read, write, Description("Read Total of GPIOs.")] void ReadTotalofGPIOs([out] uint32 argr);
    [WmiMethodId(34), Implemented, read, write, Description("Read GPIO pin Status.")] void ReadGPIOpPinStatus([in] uint32 arg2, [out] uint32 argr);
    [WmiMethodId(35), Implemented, read, write, Description("Read Chassis Color.")] void ReadChassisColor([out] uint32 argr);
    [WmiMethodId(36), Implemented, read, write, Description("Read Platform Properties.")] void ReadPlatformProperties([out] uint32 argr);
    [WmiMethodId(37), Implemented, read, write, Description("Game Shift Status.")] void GameShiftStatus([in] uint32 arg2, [out] uint32 argr);
    [WmiMethodId(49), Implemented, read, write, Description("MUX Switch.")] void MUXSwitch([in] uint32 arg2, [out] uint32 argr);
    [WmiMethodId(128), Implemented, read, write, Description("Caldera SW installation.")] void CalderaSWInstallation([out] uint32 argr);
    [WmiMethodId(129), Implemented, read, write, Description("Caldera SW is released.")] void CalderaSWReleased([out] uint32 argr);
    [WmiMethodId(130), Implemented, read, write, Description("Caldera Connection Status.")] void CalderaConnectionStatus([in] uint32 arg2, [out] uint32 argr);
    [WmiMethodId(131), Implemented, read, write, Description("Surprise Unplugged Flag Status.")] void SurpriseUnpluggedFlagStatus([out] uint32 argr);
    [WmiMethodId(132), Implemented, read, write, Description("Clear Surprise Unplugged Flag.")] void ClearSurpriseUnpluggedFlag([out] uint32 argr);
    [WmiMethodId(133), Implemented, read, write, Description("Cancel Undock Request.")] void CancelUndockRequest([out] uint32 argr);
    [WmiMethodId(135), Implemented, read, write, Description("Devices in Caldera.")] void DevicesInCaldera([in] uint32 arg2, [out] uint32 argr);
    [WmiMethodId(136), Implemented, read, write, Description("Notify BIOS for SW ready to disconnect Caldera.")] void NotifyBIOSForSWReadyToDisconnectCaldera([out] uint32 argr);
    [WmiMethodId(160), Implemented, read, write, Description("Tobii SW installation.")] void TobiiSWinstallation([out] uint32 argr);
    [WmiMethodId(161), Implemented, read, write, Description("Tobii SW Released.")] void TobiiSWReleased([out] uint32 argr);
    [WmiMethodId(162), Implemented, read, write, Description("Tobii Camera Power Reset.")] void TobiiCameraPowerReset([out] uint32 argr);
    [WmiMethodId(163), Implemented, read, write, Description("Tobii Camera Power On.")] void TobiiCameraPowerOn([out] uint32 argr);
    [WmiMethodId(164), Implemented, read, write, Description("Tobii Camera Power Off.")] void TobiiCameraPowerOff([out] uint32 argr);
}; 
```

In fetching the mof, there are several ways,

1. WMI
2. decomplie bios dump.

There are many tools can be used to fetch mof info. But I'm still confused with the difference between.

Being a newbie to windows driver development, I'm confused with all these things, I just tried as much as I could.

From the `alienfan-cli.exe dump`, we know there are many functions in the wmi class, but only with some basic info, I don't how these methed will be excuted, what arg(s) should I will pass, etc..

In the very beginning, the author recommand using RW-everything to dump ACPI table.

Sadly, RW cannot be used on my laptop, I tried to fix this in many ways, all failed.

So I had to find other ways.

With the help of ChatGPT, I did find some ways.

### How to view the WMI class info

There are tools in windows. f.e., [WmiExplorer](https://github.com/vinaypamnani/wmie2), [wbemtest](https://learn.microsoft.com/en-us/intune/configmgr/develop/core/understand/introduction-to-wbemtest), etc..

In `WmiExplorer.exe`:

![WmiExplorer](/assets/img/posts/Snipaste_2025-07-05_15-27-01.png)

In `wbemtest.exe`:

![WmiExplorer](/assets/img/posts/Snipaste_2025-07-05_15-30-24.png)

as I said before, with these tools, we only know the basic info.

### Dump ACPI Table

We need to how these methods are implemented, so we have to fetch the ACPI table.

Since I could not use RE-everything in win11, so I found some other ways.

First, downlaod [iasl](https://acpica.org/downloads) tool, and dump all tables with:

```shell
acpidump.exe -b
```

This command will produces many files, like `apic.dat`, `bgrt.dat`, `boot.dat`, `dbg2.dat`, `dsdt.dat`, `ssdt.dat`, `ssdt1.dat`, etc..

Next, decompile these `.dat` files with:

```shell
iasl.exe -d dsdt.dat
iasl.exe -d ssdt.dat
...
```

This command will produce `dsdt.dsl`, `ssdt.dsl`, etc.. These are readable files vs IDE like VS code.

What I'm intersted locates in the `ssdt1.dsl`, which begins with these codes:

```c++
/*
 * Intel ACPI Component Architecture
 * AML/ASL+ Disassembler version 20250404 (32-bit version)
 * Copyright (c) 2000 - 2025 Intel Corporation
 * 
 * Disassembling to symbolic ASL+ operators
 *
 * Disassembly of ssdt1.dat
 *
 * Original Table Header:
 *     Signature        "SSDT"
 *     Length           0x00001FBF (8127)
 *     Revision         0x02
 *     Checksum         0xBF
 *     OEM ID           "ALWARE"
 *     OEM Table ID     "AWCCTABL"
 *     OEM Revision     0x00001000 (4096)
 *     Compiler ID      "INTL"
 *     Compiler Version 0x20200717 (538969879)
 */
DefinitionBlock ("", "SSDT", 2, "ALWARE", "AWCCTABL", 0x00001000)
{
    External (_SB_.AMW0.WMI_, MethodObj)    // 2 Arguments
    ...
    Scope (\_SB)
    {
        Device (AMWW)
        {
            Name (_HID, "PNP0C14" /* Windows Management Instrumentation Device */)  // _HID: Hardware ID
            Name (_UID, "AWCC")  // _UID: Unique ID
            Name (_WDG, Buffer (0x28)
            {
                /* 0000 */  0xCE, 0x91, 0x05, 0xA7, 0x97, 0xA9, 0xDA, 0x11,  // ........
                /* 0008 */  0xB0, 0x12, 0xB6, 0x22, 0xA1, 0xEF, 0x54, 0x92,  // ..."..T.
                /* 0010 */  0x41, 0x58, 0x01, 0x02, 0x21, 0x12, 0x90, 0x05,  // AX..!...
                /* 0018 */  0x66, 0xD5, 0xD1, 0x11, 0xB2, 0xF0, 0x00, 0xA0,  // f.......
                /* 0020 */  0xC9, 0x06, 0x29, 0x10, 0x4D, 0x4F, 0x01, 0x00   // ..).MO..
            })
            ...
            Method (WMAX, 3, Serialized)
            {
                CreateByteField (Arg2, Zero, BFB0)
                CreateByteField (Arg2, One, BFB1)
                CreateByteField (Arg2, 0x02, BFB2)
                If ((Arg1 == 0x1A))
                {
                    If ((BFB0 == One))
                    {
                        Local0 = AX01 (BFB1)
                    }
                    ElseIf ((BFB0 == 0x02))
                    {
                        Local0 = AX02 (BFB1, BFB2)
                    }
                    ElseIf ((BFB0 == 0x03))
                    {
                        Local0 = AX03 (BFB1, BFB2)
                    }
                    Else
                    {
                        Local0 = 0xFFFFFFFF
                    }

                    Return (Local0)
                }
                ...
```

This ACPI table implements the methods of the WMI class `AWCCWmiMethodFunction` by the method `Method (WMAX, 3, Serialized)`.

In this method, it dispatches methods with `Arg1`.

Based on the `alienfx-tool`, I craeted a test c++ project to test. In my c++ test project:

```c++
// Execute the method
IWbemClassObject* pOutParams = nullptr;
//LogExecMethodParameters(pInParams); // Log input parameters
hr = pSvc->ExecMethod(
    pathVar.bstrVal,
    BSTR(methodName),
    0,
    NULL,
    pInParams,
    &pOutParams,
    NULL
);
```

Here, `pathVar` is the instance path of the WMI class `AWCCWmiMethodFunction`, `methodName` is the method name (f.e., `SystemInformation`, `TccControl`, etc.).

Here, I pass the method name, which is string-like, to the `ExecMethod`.

But in the ACPI Table, it dispathes the methods by `Arg1`, which is a hexadecimal number.

However, at that time, I didn't understand the relationship between WMI and ACPI. So I didn't understand how the method name (string) is mapped to `Arg1` (hex). And I tried to find a `mapping table`, with the help of ChatGPT.

### Dump BIOS

I download the `CSME System Tools v16.1 r0`. I need the `Flash Programming Tool` inside it, which is `FPTW64.exe`.

Instead of dumping all regions, I just dumped only the BIOS,

```shell
FPTW64.exe -bios -d bios.bin
```

This command produced a `bios.bin` file.

Any I need to analyze this `bios.bin` file.

So I downloaded `UEFITool`, and opened the `bios.bin` in it.

Then through search, I located some interesting parts related to `AWCC`, f.e. `AwccWmiServiceSmm`, `AwccWmiInterface`, `AwccWmiInterfaceAcpi`.

I extracted these parts, and tried to analyze them with tools like `Ghidra` and `IDA Pro`, but failed. At least I learned some basic operations of these tools.

Yes, because I knew little about WMI, ACPI, etc,. So I tried to find a `mapping table` at that time.

### Offical WMI ACPI Sample

Until I found the [WMI ACPI Sample](https://learn.microsoft.com/en-us/samples/microsoft/windows-driver-samples/wmi-acpi-sample/), which can be found in the microsoft offical site.

And this is [repo](github.com/microsoft/windows-driver-samples/tree/main/wmi/wmiacpi) of the offical sample.

In this repo, there is a `wmi-acpi.htm` file, which is `The Windows Instrumentation: WMI and ACPI white paper.`.

From this white paper, I finally understood something about WMI and ACPI (although this paper is about windows 2000), especially some programming specifications of ACPI (the .dsl file mentioned above).

F.e, 

1. `Name (_WDG)` / `Method (_WDG)`.
2. Method `WQxx`, `WSxx`, etc..

In my situation, in `ssdt1.dsl`, the `_WDG` part is
```c++
Name (_WDG, Buffer (0x28)
{
    /* 0000 */  0xCE, 0x91, 0x05, 0xA7, 0x97, 0xA9, 0xDA, 0x11,  // ........
    /* 0008 */  0xB0, 0x12, 0xB6, 0x22, 0xA1, 0xEF, 0x54, 0x92,  // ..."..T.
    /* 0010 */  0x41, 0x58, 0x01, 0x02, 0x21, 0x12, 0x90, 0x05,  // AX..!...
    /* 0018 */  0x66, 0xD5, 0xD1, 0x11, 0xB2, 0xF0, 0x00, 0xA0,  // f.......
    /* 0020 */  0xC9, 0x06, 0x29, 0x10, 0x4D, 0x4F, 0x01, 0x00   // ..).MO..
})
```

According to the white paper, this `_WDG` part contains two parts.

---

The 1st part.

The first 16 bytes (0xCE, 0x91, 0x05, 0xA7, 0x97, 0xA9, 0xDA, 0x11, 0xB0, 0x12, 0xB6, 0x22, 0xA1, 0xEF, 0x54, 0x92), is the GUID for the WMI interface itself.

So the GUID is: `{A70591CE-A997-11DA-B012-B622A1EF5492}`.

The 2 bytes at offset 0x10 (0x41, 0x58), is the Object ID, (0x41 for 'A', 0x58 for 'X').

The byte at offset 0x12 (0x01) is the InstanceCount.

The byte at offset 0x13 (0x02) is the Flags.

---

The 2nd part.

The first 16 bytes (0x21, 0x12, 0x90, 0x05, 0x66, 0xD5, 0xD1, 0x11, 0xB2, 0xF0, 0x00, 0xA0, 0xC9, 0x06, 0x29, 0x10), is the GUID for the ACPI method block.

The GUID is: `{05901221-D566-11D1-F0B2-00A0C9062910}`. But I cannot find this GUID in the UEFITool.

The 2 bytes at offset 0x10 (0x4D, 0x4F) is the Object ID, (0x4D for 'M', 0x4F for 'O').

The byte at offset 0x12 (0x01) is the InstanceCount.

The byte at offset 0x13 (0x00) is the Flags.

---

The 1st part, its GUID matched the GUID of the WMI class `AWCCWmiMethodFunction`, this means, when wmi method is invoked in the system, this acpi table will be loacted.

As for the 2nd part, through some searching, the GUID `{05901221-D566-11D1-F0B2-00A0C9062910}` seems to be defined by Microsoft, which is for returning the MOF data.

Let's continues on the 1st part.

According to the white paper, the Object ID (`xx`) tells the firmware to invoke `WMxx` method. Thus, the 1st part's Object ID is `AX`, which means, `Method (WMAX, 3, Serialized)` will be invoked next.

According to the white paper, 

> By convention, the name of the control method is WMxx, where xx is the 2-character ID that maps to the GUID. This method call has three parameters; the first is a ULONG that has the instance index being executed; the second contains the method ID for the method being executed; and the third is a buffer that contains the input for the method call.

At this point, I have a clearer understanding of the relationship between WMI and ACPI, which also explains why I tried to reverse engineer the BIOS to find some `mapping table` between the `method name` with `Arg1`, but found no results.

As mentioned before, when viewing the mof info through the WMI, we know each method of the class `AWCCWmiMethodFunction` has a method id, which is deciaml, we should convert it to hex to match the `Arg1` conditions. F.e.,

1. The method id of `SystemInformation` is `26` (`0x1A` in hex), which matches `If ((Arg1 == 0x1A))` is `ssdt1.dsl`.
2. The method id of `TccControl` is `30` (`0x1E` in hex), which matches `If ((Arg1 == 0x1E))` in `ssdt1.dsl`.

However, for the submethods of each method, which are further dispatched by `Arg2`, it seems that I have to guess and test based ont the code in the `ssdt1.dsl`. This has been done very well by the author of `alienfx-tool`.

Or, maybe I should deep down into the `bios.bin` file with `Ghidra` or `IDA Pro`.

### Other things

1. The pdf file of `ACPI Spec v6.6` has 1202 pages in total, I'm still reading it.
2. Another tool [bmfdec](https://github.com/pali/bmfdec) can be used dump the mof info from the ACPI, not from WMI as the tools metioned before. The usage of this tool can be found [here](https://github.com/pali/bmfdec/issues/2).

```shell
sudo cat /sys/bus/wmi/drivers/wmi-bmof/..../bmof | ./bmf2mof > wmi.mof
```

There are many folders in the `/sys/bus/wmi/drivers/wmi-bmof/`, in most of these folders, there is a `bmof` file.

This tool can only be used in real-machine.

This tool cannot be used in the VM, since there wont be such folders existing.

## Cheat Sheet

| Abbr. | Meaning |
| --- | --- |
| ACPI | Advanced Configuration and Power Interface |
| MOF | Managed Object Format |
| WMI | Windows Management Instrumentation |
