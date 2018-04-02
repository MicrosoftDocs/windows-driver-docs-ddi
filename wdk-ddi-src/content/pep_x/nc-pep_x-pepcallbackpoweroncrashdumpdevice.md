---
UID: NC:pep_x.PEPCALLBACKPOWERONCRASHDUMPDEVICE
title: PEPCALLBACKPOWERONCRASHDUMPDEVICE
author: windows-driver-content
description: The PowerOnDumpDeviceCallback callback routine turns on the crash-dump device.
old-location: kernel\powerondumpdevicecallback.htm
old-project: kernel
ms.assetid: 83E5D362-BC3C-4480-9904-6ABBB26DAFF2
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: PEPCALLBACKPOWERONCRASHDUMPDEVICE, PowerOnDumpDeviceCallback, PowerOnDumpDeviceCallback routine [Kernel-Mode Driver Architecture], kernel.powerondumpdevicecallback, pepfx/PowerOnDumpDeviceCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: pep_x.h
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	pepfx.h
api_name:
-	PowerOnDumpDeviceCallback
product: Windows
targetos: Windows
req.typenames: PO_FX_CORE_DEVICE, *PPO_FX_CORE_DEVICE
---

# PEPCALLBACKPOWERONCRASHDUMPDEVICE callback


## -description


The <i>PowerOnDumpDeviceCallback</i> callback routine turns on the crash-dump device.


## -parameters




### -param CrashdumpInformation [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt186708">PEP_CRASHDUMP_INFORMATION</a> structure that contains information about the crash-dump device.


## -returns



This routine returns TRUE if it succeeds in turning on power to the crash-dump device. Otherwise, it returns FALSE.




## -remarks



This routine is implemented by the platform extension plug-in (PEP). The routine handles requests from the Windows kernel to turn on the crash-dump device so that a crash dump can be saved to disk.

The PEP registers its <i>PowerOnDumpDeviceCallback</i> routine in response to a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_CRASHDUMP_DEVICE</a> notification from the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx).

The <i>PowerOnDumpDeviceCallback</i> routine is called at IRQL = HIGH_LEVEL with interrupts disabled. Thus, this routine cannot use timers, events, or any synchronization primitives other than spin locks.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186708">PEP_CRASHDUMP_INFORMATION</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_CRASHDUMP_DEVICE</a>
 

 

