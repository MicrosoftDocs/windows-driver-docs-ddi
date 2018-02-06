---
UID: NF:wdm.PoFxSetComponentResidency
title: PoFxSetComponentResidency function
author: windows-driver-content
description: The PoFxSetComponentResidency routine sets the estimated time for how long a component is likely to remain idle after the component enters the idle condition.
old-location: kernel\pofxsetcomponentresidency.htm
old-project: kernel
ms.assetid: B4216BA1-FC5C-4A3B-BB74-E071BD2048F8
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PoFxSetComponentResidency, kernel.pofxsetcomponentresidency, wdm/PoFxSetComponentResidency, PoFxSetComponentResidency routine [Kernel-Mode Driver Architecture]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Ntoskrnl.exe
apiname:
-	PoFxSetComponentResidency
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# PoFxSetComponentResidency function


## -description


The <b>PoFxSetComponentResidency</b> routine sets the estimated time for how long a component is likely to remain idle after the component enters the idle condition.


## -syntax


````
VOID PoFxSetComponentResidency(
  _In_ POHANDLE  Handle,
  _In_ ULONG     Component,
  _In_ ULONGLONG Residency
);
````


## -parameters




### -param Handle [in]

A handle that represents the registration of the device with the power management framework (PoFx). The device driver previously received this handle from the <a href="..\wdm\nf-wdm-pofxregisterdevice.md">PoFxRegisterDevice</a> routine.


### -param Component [in]

The index that identifies the component. This parameter is an index into the <b>Components</b> array in the <a href="..\wdm\ns-wdm-_po_fx_device_v1.md">PO_FX_DEVICE</a> structure that the device driver used to register the device with PoFx. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


### -param Residency [in]

The estimated residency time, in 100-nanosecond units. This parameter is a hint to PoFx about how long the component is likely to remain idle after a transition from the active condition to the idle condition. For more information, see Remarks.


## -returns


None.



## -remarks


The calling driver supplies an estimated residency time that PoFx can use as a hint to improve performance. PoFx uses this hint to select an appropriate low-power Fx state for a component that is in the idle condition.

The device driver can call <b>PoFxSetComponentResidency</b> each time a change in circumstances requires a change in the estimated residency time. After each call, the new estimated residency time remains in effect until the driver calls <b>PoFxSetComponentResidency</b> again to update it.

If a component is in the idle condition when <b>PoFxSetComponentResidency</b> is called, PoFx might change the component’s Fx state to accommodate the new estimated residency time specified by the caller.


