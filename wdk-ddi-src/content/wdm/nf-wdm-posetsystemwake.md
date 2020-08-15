---
UID: NF:wdm.PoSetSystemWake
title: PoSetSystemWake function (wdm.h)
description: The PoSetSystemWake routine marks the specified IRP as one that contributed to waking the system from a sleep state.
old-location: kernel\posetsystemwake.htm
tech.root: kernel
ms.assetid: e79ed9a1-b271-4c0a-a82f-9fecab930569
ms.date: 04/30/2018
keywords: ["PoSetSystemWake function"]
ms.keywords: PoSetSystemWake, PoSetSystemWake routine [Kernel-Mode Driver Architecture], kernel.posetsystemwake, portn_09bfa419-5a6c-4305-87ee-58a0e032d0c4.xml, wdm/PoSetSystemWake
f1_keywords:
 - "wdm/PoSetSystemWake"
 - "PoSetSystemWake"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- PoSetSystemWake
targetos: Windows
req.typenames: 
---

# PoSetSystemWake function


## -description


The <b>PoSetSystemWake</b> routine marks the specified IRP as one that contributed to waking the system from a sleep state.


## -parameters




### -param Irp 
[in, out]
A pointer to the wait/wake IRP.


## -remarks



Drivers call <b>PoSetSystemWake</b> to mark an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-wait-wake">IRP_MN_WAIT_WAKE</a> IRP as contributing to waking the system from a sleep state. By default, wait/wake IRPs are considered to be device wake-up IRPs. It is the responsibility of the terminal device in a wait/wake chain to determine if it woke the system and to call <b>PoSetSystemWake</b> for the terminal wait/wake IRP. When a driver calls <b>PoSetSystemWake</b> on an IRP, it is marked as having contributed to waking the system from a sleep state. Only one driver in a stack needs to call this routine, and it should normally be the bus driver in a driver stack.

All other drivers in a wait/wake chain can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pogetsystemwake">PoGetSystemWake</a> for their own wait/wake IRPs at completion to determine if they should call <b>PoSetSystemWake</b> on any child wait/wake IRPs that they are about to complete. This ensures that system wake information properly progresses throughout the wait/wake chain.

After a wait/wake IRP completes, the power manager checks if the IRP is marked as a system wake IRP. If the IRP is marked as a system wake IRP, the power manager adds the IRP to an internal list of the devices that woke the system. However, the power manager only keeps track of the most specific devices that work the system. For example, if device A is added as a device that woke the system, and then device B—a child of device A—is also added, the power manager only retains device B in the list because device B is the most specific. If the power manager cannot determine the most specific device that woke the system, the power manager might keep track of more than one device that reported it woke the system.

The power manager logs an Event Tracing for Windows (ETW) event (viewable in the global system channel) that includes information about which devices woke the system.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pogetsystemwake">PoGetSystemWake</a>
 

 

