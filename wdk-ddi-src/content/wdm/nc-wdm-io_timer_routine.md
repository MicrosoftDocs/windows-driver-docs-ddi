---
UID: NC:wdm.IO_TIMER_ROUTINE
title: IO_TIMER_ROUTINE
author: windows-driver-content
description: The IoTimer routine is a DPC that, if registered, is called once per second.
old-location: kernel\iotimer.htm
old-project: kernel
ms.assetid: c41b7489-afd2-4ddf-b296-6d42e3ff6cbf
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.iotimer, IoTimer routine [Kernel-Mode Driver Architecture], IoTimer, IO_TIMER_ROUTINE, IO_TIMER_ROUTINE, wdm/IoTimer, DrvrRtns_e0e54c40-37d6-41b3-8374-b1a7763d54ed.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.irql: Called at DISPATCH_LEVEL (see Remarks section).
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdm.h
apiname:
-	IoTimer
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# IO_TIMER_ROUTINE callback


## -description


The <i>IoTimer</i> routine is a DPC that, if registered, is called once per second.


## -prototype


````
IO_TIMER_ROUTINE IoTimer;

VOID IoTimer(
  _In_     struct DEVICE_OBJECT *DeviceObject,
  _In_opt_ PVOID                Context
)
{ ... }
````


## -parameters




### -param *DeviceObject [in]

Caller-supplied pointer to a <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure. This is the device object for the target device, previously created by the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routine.


### -param Context [in, optional]

Caller-supplied pointer to driver-defined context information, specified in a previous call to <a href="..\wdm\nf-wdm-ioinitializetimer.md">IoInitializeTimer</a>.


## -returns


None



## -remarks


A driver's <i>IoTimer</i> routine executes in a DPC context, at IRQL = DISPATCH_LEVEL.

A driver can associate an <i>IoTimer</i> routine with each device object it creates. (You can use a single <i>IoTimer</i> routine with multiple device objects, or a separate routine with each device object.) To register an <i>IoTimer</i> routine, a driver must call <a href="..\wdm\nf-wdm-ioinitializetimer.md">IoInitializeTimer</a>, supplying the <i>IoTimer</i> routine's address and a device object pointer.

To queue an <i>IoTimer</i> routine for execution, a driver routine must call <a href="..\wdm\nf-wdm-iostarttimer.md">IoStartTimer</a>. The system calls the <i>IoTimer</i> routine once per second until the driver calls <a href="..\wdm\nf-wdm-iostoptimer.md">IoStopTimer</a>.

For more information about <i>IoTimer</i> routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550386">IoTimer Routines</a>.


