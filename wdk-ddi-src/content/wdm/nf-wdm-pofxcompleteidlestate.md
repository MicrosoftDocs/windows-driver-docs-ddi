---
UID: NF:wdm.PoFxCompleteIdleState
title: PoFxCompleteIdleState function
author: windows-driver-content
description: The PoFxCompleteIdleState routine informs the power management framework (PoFx) that the specified component has completed a pending change to an Fx state.
old-location: kernel\pofxcompleteidlestate.htm
old-project: kernel
ms.assetid: D9224991-DB36-4250-861A-6C21E29F91EF
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PoFxCompleteIdleState, PoFxCompleteIdleState routine [Kernel-Mode Driver Architecture], kernel.pofxcompleteidlestate, wdm/PoFxCompleteIdleState
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
-	PoFxCompleteIdleState
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# PoFxCompleteIdleState function


## -description


The <b>PoFxCompleteIdleState</b> routine informs the power management framework (PoFx) that the specified component has completed a pending change to an Fx state.


## -syntax


````
VOID PoFxCompleteIdleState(
  _In_ POHANDLE Handle,
  _In_ ULONG    Component
);
````


## -parameters




### -param Handle [in]

A handle that represents the registration of the device with PoFx. The device driver previously received this handle from the <a href="..\wdm\nf-wdm-pofxregisterdevice.md">PoFxRegisterDevice</a> routine.


### -param Component [in]

The index that identifies the component. This parameter is an index into the <b>Components</b> array in the <a href="..\wudfwdm\ns-wudfwdm-_po_fx_device_v1.md">PO_FX_DEVICE</a> structure that the device driver used to register the device with PoFx. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


## -returns



None,




## -remarks



After PoFx calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh450931">ComponentIdleStateCallback</a> callback routine, the driver must respond by calling <b>PoFxCompleteIdleState</b>.

PoFx calls the driver's <i>ComponentIdleStateCallback</i> routine to tell the driver to switch the specified component to a new Fx power state. After the driver completes the transition to the new Fx state, the driver calls <b>PoFxCompleteIdleState</b> to inform PoFx. The <b>PoFxCompleteIdleState</b> call can occur either during or after the <i>ComponentIdleStateCallback</i> call.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450931">ComponentIdleStateCallback</a>



<a href="..\wdm\nf-wdm-pofxregisterdevice.md">PoFxRegisterDevice</a>



<a href="..\wudfwdm\ns-wudfwdm-_po_fx_device_v1.md">PO_FX_DEVICE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PoFxCompleteIdleState routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

