---
UID: NF:wdm.PoFxCompleteIdleCondition
title: PoFxCompleteIdleCondition function
author: windows-driver-content
description: The PoFxCompleteIdleCondition routine informs the power management framework (PoFx) that the specified component has completed a pending change to the idle condition.
old-location: kernel\pofxcompleteidlecondition.htm
old-project: kernel
ms.assetid: D43DA9A4-02F4-4C4E-83AE-DFADA0FCC73D
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PoFxCompleteIdleCondition
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
req.alt-api: PoFxCompleteIdleCondition
req.alt-loc: Ntoskrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntoskrnl.lib
req.dll: Ntoskrnl.exe
req.irql: <= DISPATCH_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# PoFxCompleteIdleCondition function



## -description
The <b>PoFxCompleteIdleCondition</b> routine informs the power management framework (PoFx) that the specified component has completed a pending change to the idle condition.



## -syntax

````
VOID PoFxCompleteIdleCondition(
  _In_ POHANDLE Handle,
  _In_ ULONG    Component
);
````


## -parameters

### -param Handle [in]

A handle that represents the registration of the device with PoFx. The device driver previously received this handle from the <a href="..\wdm\nf-wdm-pofxregisterdevice.md">PoFxRegisterDevice</a> routine.


### -param Component [in]

The index that identifies the component. This parameter is an index into the <b>Components</b> array in the <a href="..\wdm\ns-wdm-_po_fx_device_v1.md">PO_FX_DEVICE</a> structure that the device driver used to register the device with PoFx. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


## -returns
None.


## -remarks
After PoFx calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh406420">ComponentIdleConditionCallback</a> callback routine, the driver must respond by calling <b>PoFxCompleteIdleCondition</b>.

When PoFx calls the driver's <i>ComponentIdleConditionCallback</i> routine, the driver initiates a transition to the idle condition in the specified component. After this transition is complete, the driver calls <b>PoFxCompleteIdleCondition</b> to notify PoFx. The <b>PoFxCompleteIdleCondition</b> call can occur either during or after the <i>ComponentIdleConditionCallback</i> call.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406420">ComponentIdleConditionCallback</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_po_fx_device_v1.md">PO_FX_DEVICE</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-pofxregisterdevice.md">PoFxRegisterDevice</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PoFxCompleteIdleCondition routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

