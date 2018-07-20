---
UID: NF:wdm.PoFxSetDeviceIdleTimeout
title: PoFxSetDeviceIdleTimeout function
author: windows-driver-content
description: The PoFxSetDeviceIdleTimeout routine specifies the minimum time interval from when the last component of the device enters the idle condition to when the power management framework (PoFx) calls the driver's DevicePowerNotRequiredCallback routine.
old-location: kernel\pofxsetdeviceidletimeout.htm
tech.root: kernel
ms.assetid: 8378D5F1-92AC-4C59-BA66-68246C011199
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: PoFxSetDeviceIdleTimeout, PoFxSetDeviceIdleTimeout routine [Kernel-Mode Driver Architecture], kernel.pofxsetdeviceidletimeout, wdm/PoFxSetDeviceIdleTimeout
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: Ntoskrnl.lib
req.dll: Ntoskrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Ntoskrnl.exe
api_name:
-	PoFxSetDeviceIdleTimeout
product:
- Windows
targetos: Windows
req.typenames: 
---

# PoFxSetDeviceIdleTimeout function


## -description


The <b>PoFxSetDeviceIdleTimeout</b> routine specifies the minimum time interval from when the last component of the device enters the idle condition to when the power management framework (PoFx) calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh450946">DevicePowerNotRequiredCallback</a> routine.


## -parameters




### -param Handle [in]

A handle that represents the registration of the device with PoFx. The device driver previously received this handle from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439521">PoFxRegisterDevice</a> routine.


### -param IdleTimeout [in]

The idle time-out interval in 100-nanosecond units. For more information, see Remarks.


## -returns



None.




## -remarks



This routine specifies a time-out interval for PoFx to apply to future calls to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh450946">DevicePowerNotRequiredCallback</a> callback routine. By default, this time-out interval is zero, in which case PoFx might call the <i>DevicePowerNotRequiredCallback</i> routine just as soon as the device is ready to switch to a low-power Dx state. However, a driver might prefer to delay this transition and to keep the device in the D0 power state for some additional time-out interval. In this case, if the device becomes active before the end of the time-out interval, and is therefore required to stay in the D0 state, the pending <i>DevicePowerNotRequiredCallback</i> call is no longer required and is canceled by PoFx.

For example, to improve performance and reduce wear, a storage device driver might want to prevent a spinning drive from entering D3 and slowing down until the drive has been idle for a sufficiently long time. To simplify this driver's implementation of the <i>DevicePowerNotRequiredCallback</i> callback routine, the <b>PoFxSetDeviceIdleTimeout</b> routine enables the driver to automatically delay the D3 transition without requiring the driver to set up a timer.

The time-out interval starts when all components of the device complete their transitions to the idle condition. Typically, PoFx waits until the end of the time-out interval to call the <i>DevicePowerNotRequiredCallback</i> routine. However, if PoFx is preparing to enter a low-power system state, PoFx might end the time-out interval early. In any case, when PoFx calls the driver's <i>DevicePowerNotRequiredCallback</i> routine, the driver should switch to the low-power Dx state without further delay.

The device driver can call <b>PoFxSetDeviceIdleTimeout</b> each time a change in conditions requires a change in the idle time-out interval. After each call, the new idle time-out interval remains in effect until the driver calls <b>PoFxSetDeviceIdleTimeout</b> again to update it.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450946">DevicePowerNotRequiredCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439521">PoFxRegisterDevice</a>
 

 

