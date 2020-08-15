---
UID: NC:pepfx.PEPCALLBACKPOWERONCRASHDUMPDEVICE
title: PEPCALLBACKPOWERONCRASHDUMPDEVICE (pepfx.h)
description: The PowerOnDumpDeviceCallback callback routine turns on the crash-dump device.
old-location: kernel\powerondumpdevicecallback.htm
tech.root: kernel
ms.assetid: 83E5D362-BC3C-4480-9904-6ABBB26DAFF2
ms.date: 04/30/2018
keywords: ["PEPCALLBACKPOWERONCRASHDUMPDEVICE callback function"]
ms.keywords: PEPCALLBACKPOWERONCRASHDUMPDEVICE, PowerOnDumpDeviceCallback, PowerOnDumpDeviceCallback routine [Kernel-Mode Driver Architecture], kernel.powerondumpdevicecallback, pepfx/PowerOnDumpDeviceCallback
f1_keywords:
 - "pepfx/PowerOnDumpDeviceCallback"
 - "PowerOnDumpDeviceCallback"
req.header: pepfx.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.lib: 
req.dll: 
req.irql: Called at HIGH_LEVEL.
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- pepfx.h
api_name:
- PowerOnDumpDeviceCallback
targetos: Windows
req.typenames: 
---

# PEPCALLBACKPOWERONCRASHDUMPDEVICE callback function


## -description


The <i>PowerOnDumpDeviceCallback</i> callback routine turns on the crash-dump device.


## -parameters




### -param CrashdumpInformation 
[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_crashdump_information">PEP_CRASHDUMP_INFORMATION</a> structure that contains information about the crash-dump device.


## -returns



This routine returns TRUE if it succeeds in turning on power to the crash-dump device. Otherwise, it returns FALSE.




## -remarks



This routine is implemented by the platform extension plug-in (PEP). The routine handles requests from the Windows kernel to turn on the crash-dump device so that a crash dump can be saved to disk.

The PEP registers its <i>PowerOnDumpDeviceCallback</i> routine in response to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_CRASHDUMP_DEVICE</a> notification from the Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx).

The <i>PowerOnDumpDeviceCallback</i> routine is called at IRQL = HIGH_LEVEL with interrupts disabled. Thus, this routine cannot use timers, events, or any synchronization primitives other than spin locks.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_crashdump_information">PEP_CRASHDUMP_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_CRASHDUMP_DEVICE</a>
 

 

