---
UID: NF:wdm.PoQueryWatchdogTime
title: PoQueryWatchdogTime function (wdm.h)
description: The PoQueryWatchdogTime routine indicates whether the power manager has enabled a watchdog time-out counter for any power IRP that is currently assigned to the device stack.
old-location: kernel\poquerywatchdogtime.htm
tech.root: kernel
ms.assetid: 4833d4e2-295a-4d38-9ebf-8af68eeff948
ms.date: 04/30/2018
ms.keywords: PoQueryWatchdogTime, PoQueryWatchdogTime routine [Kernel-Mode Driver Architecture], kernel.poquerywatchdogtime, portn_1fe369ed-f8f0-4459-943f-a624764c279b.xml, wdm/PoQueryWatchdogTime
ms.topic: function
f1_keywords:
 - "wdm/PoQueryWatchdogTime"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- PoQueryWatchdogTime
product:
- Windows
targetos: Windows
req.typenames: 
---

# PoQueryWatchdogTime function


## -description


The <b>PoQueryWatchdogTime</b> routine indicates whether the power manager has enabled a watchdog time-out counter for any power IRP that is currently assigned to the device stack.


## -parameters




### -param Pdo [in]

A pointer to a physical device object (PDO). This parameter points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure that represents a physical device.


### -param SecondsRemaining [out]

A pointer to a location into which the routine writes the time, in seconds, that remains before the next power watchdog time-out is set to occur.


## -returns



<b>PoQueryWatchdogTime</b> returns <b>TRUE</b> if a watchdog-enabled power IRP is currently assigned to the device stack. Otherwise, it returns <b>FALSE</b>.




## -remarks



This routine enables kernel-mode drivers to monitor watchdog time-out counters that the power manager has enabled to keep track of power IRPs that it has issued. If one or more watchdog time-out counters are currently enabled, the routine returns <b>TRUE</b> and provides the amount of time that remains before the next time-out.

For example, a driver that experiences delays when shutting down a device can call this routine to determine how much time remains before the driver must respond to a power IRP to prevent a controlled shutdown (a bug check) of the operating system.

The power manager sets a watchdog time-out counter when it issues a power IRP to the device stack. The time-out period for this counter is typically several minutes. If a device in the stack is unresponsive and causes the IRP to stall for the time-out period, the power manager treats this condition as an unrecoverable error and initiates a controlled shutdown of the operating system.

If more than one power watchdog time-out is currently enabled, the routine sets *<i>SecondsRemaining</i> to the time that remains to the next time-out.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>
 

 

