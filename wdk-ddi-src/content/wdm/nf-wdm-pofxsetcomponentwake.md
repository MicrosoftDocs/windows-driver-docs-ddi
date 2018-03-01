---
UID: NF:wdm.PoFxSetComponentWake
title: PoFxSetComponentWake function
author: windows-driver-content
description: The PoFxSetComponentWake routine indicates whether the driver arms the specified component to wake whenever the component enters the idle condition.
old-location: kernel\pofxsetcomponentwake.htm
old-project: kernel
ms.assetid: BE2E35B0-1C34-4740-ABED-4E96F8908174
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PoFxSetComponentWake, PoFxSetComponentWake routine [Kernel-Mode Driver Architecture], kernel.pofxsetcomponentwake, wdm/PoFxSetComponentWake
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
-	PoFxSetComponentWake
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# PoFxSetComponentWake function


## -description


The <b>PoFxSetComponentWake</b> routine indicates whether the driver arms the specified component to wake whenever the component enters the idle condition.


## -syntax


````
VOID PoFxSetComponentWake(
  _In_ POHANDLE Handle,
  _In_ ULONG    Component,
  _In_ BOOLEAN  WakeHint
);
````


## -parameters




### -param Handle [in]

A handle that represents the registration of the device with the power management framework (PoFx). The device driver previously received this handle from the <a href="..\wdm\nf-wdm-pofxregisterdevice.md">PoFxRegisterDevice</a> routine.


### -param Component [in]

The index that identifies the component. This parameter is an index into the <b>Components</b> array in the <a href="..\wudfwdm\ns-wudfwdm-_po_fx_device_v1.md">PO_FX_DEVICE</a> structure that the device driver used to register the device with PoFx. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


### -param WakeHint [in]

Whether the driver arms the component to wake whenever the component enters the idle condition. If TRUE, the driver arms the component to wake. If FALSE, the driver does not arm the component to wake.


## -returns



None.




## -remarks



Before a component enters a low-power Fx state, the driver might arm the component to automatically wake in response to an input signal from an external source (for example, if the user pushes a button). The <i>WakeHint</i> parameter informs PoFx whether the driver arms the component to wake. If a component is armed to wake, PoFx will not switch the component to a low-power Fx state from which the component cannot wake.

When a device is registered with PoFx, the registration information for each component in the device is contained in a separate <a href="..\wudfwdm\ns-wudfwdm-_po_fx_component_v2.md">PO_FX_COMPONENT</a> structure. The <b>DeepestWakeableIdleState</b> member of this structure specifies the deepest Fx state from which the component can wake.

The device driver can call <b>PoFxSetComponentWake</b> each time a change in conditions requires a change in the <i>WakeHint</i> value. After each call, the new <i>WakeHint</i> value remains in effect until the driver calls <b>PoFxSetComponentWake</b> again to update it.


If a component is in the idle condition when <b>PoFxSetComponentWake</b> is called, PoFx might change the component’s Fx state to accommodate the new <i>WakeHint</i> parameter value specified by the caller.




## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_po_fx_component_v2.md">PO_FX_COMPONENT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PoFxSetComponentWake routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

