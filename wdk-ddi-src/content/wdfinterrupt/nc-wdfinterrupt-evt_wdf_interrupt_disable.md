---
UID: NC:wdfinterrupt.EVT_WDF_INTERRUPT_DISABLE
title: EVT_WDF_INTERRUPT_DISABLE
author: windows-driver-content
description: A driver's EvtInterruptDisable event callback function disables a specified hardware interrupt.
old-location: wdf\evtinterruptdisable.htm
old-project: wdf
ms.assetid: a9d5e3cd-2e95-4ad6-9380-64fe4df9e27f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtinterruptdisable, EvtInterruptDisable callback function, EvtInterruptDisable, EVT_WDF_INTERRUPT_DISABLE, EVT_WDF_INTERRUPT_DISABLE, wdfinterrupt/EvtInterruptDisable, DFInterruptObjectRef_4dfbc961-e1c4-494e-9e6d-d657fd5d59d9.xml, kmdf.evtinterruptdisable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "(See Remarks section.)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdfinterrupt.h
apiname:
-	EvtInterruptDisable
product: Windows
targetos: Windows
req.typenames: "*PWDF_COINSTALLER_INSTALL_OPTIONS, WDF_COINSTALLER_INSTALL_OPTIONS"
req.product: Windows 10 or later.
---

# EVT_WDF_INTERRUPT_DISABLE callback


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtInterruptDisable</i> event callback function disables a specified hardware interrupt.


## -prototype


````
EVT_WDF_INTERRUPT_DISABLE EvtInterruptDisable;

NTSTATUS EvtInterruptDisable(
  _In_ WDFINTERRUPT Interrupt,
  _In_ WDFDEVICE    AssociatedDevice
)
{ ... }
````


## -parameters




#### - Interrupt [in]

A handle to a framework interrupt object.


#### - AssociatedDevice [in]

A handle to the framework device object that the driver passed to <a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptcreate.md">WdfInterruptCreate</a>.


## -returns


The <i>EvtInterruptDisable</i> callback function must return STATUS_SUCCESS or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b> if the function encounters no errors. Otherwise, this function must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. 



## -remarks


To register an <i>EvtInterruptDisable</i> callback function, your driver must place the callback function's address in a <a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_config.md">WDF_INTERRUPT_CONFIG</a> structure before calling <a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptcreate.md">WdfInterruptCreate</a>.

The framework calls the driver's <i>EvtInterruptDisable</i> callback function each time the device leaves its working (D0) state. Additionally, a driver can cause the framework to call the <i>EvtInterruptDisable</i> callback function by calling <a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptdisable.md">WdfInterruptDisable</a>. Note that most framework-based drivers should not call <b>WdfInterruptDisable</b>, because the framework calls the driver's <i>EvtInterruptDisable</i> callback function each time the device leaves its working (D0) state.

Before calling the <i>EvtInterruptDisable</i> callback function, the framework raises the processor's IRQL to the device's DIRQL and acquires the spin lock that the driver specified in the interrupt object's <a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_config.md">WDF_INTERRUPT_CONFIG</a> structure. 

Beginning with version 1.11 of KMDF, your driver can provide <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-passive-level-interrupts">passive-level interrupt handling</a>. If the driver has requested passive-level interrupt handling, then before calling the <i>EvtInterruptDisable</i> function at IRQL = PASSIVE_LEVEL, the framework acquires the passive-level interrupt lock that the driver configured in the interrupt object's <a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_config.md">WDF_INTERRUPT_CONFIG</a> structure.

Before calling the <i>EvtInterruptDisable</i> callback function, the framework calls the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_exit_pre_interrupts_disabled.md">EvtDeviceD0ExitPreInterruptsDisabled</a> event callback function at IRQL = PASSIVE_LEVEL.

For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.



## -see-also

<a href="..\wdfinterrupt\ns-wdfinterrupt-_wdf_interrupt_config.md">WDF_INTERRUPT_CONFIG</a>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_exit_pre_interrupts_disabled.md">EvtDeviceD0ExitPreInterruptsDisabled</a>

<a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptcreate.md">WdfInterruptCreate</a>

<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_enable.md">EvtInterruptEnable</a>

<a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptdisable.md">WdfInterruptDisable</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_INTERRUPT_DISABLE callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

