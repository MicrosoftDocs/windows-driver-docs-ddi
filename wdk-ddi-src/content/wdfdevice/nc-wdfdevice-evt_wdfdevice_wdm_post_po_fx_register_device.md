---
UID: NC:wdfdevice.EVT_WDFDEVICE_WDM_POST_PO_FX_REGISTER_DEVICE
title: EVT_WDFDEVICE_WDM_POST_PO_FX_REGISTER_DEVICE
author: windows-driver-content
description: The EvtDeviceWdmPostPoFxRegisterDevice callback function performs device-specific operations after the framework has registered with the power framework.
old-location: wdf\evtdevicewdmpostpofxregisterdevice.htm
old-project: wdf
ms.assetid: 4CE227F5-9ED4-4484-AFBF-44D1260EB99D
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: EVT_WDFDEVICE_WDM_POST_PO_FX_REGISTER_DEVICE, EvtDeviceWdmPostPoFxRegisterDevice, EvtDeviceWdmPostPoFxRegisterDevice callback function, kmdf.evtdevicewdmpostpofxregisterdevice, wdf.evtdevicewdmpostpofxregisterdevice, wdfdevice/EvtDeviceWdmPostPoFxRegisterDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdfdevice.h
apiname:
-	EvtDeviceWdmPostPoFxRegisterDevice
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# EVT_WDFDEVICE_WDM_POST_PO_FX_REGISTER_DEVICE callback


## -description


<p class="CCE_Message">[Applies to KMDF only]


   The 
  <i>EvtDeviceWdmPostPoFxRegisterDevice</i> callback function performs device-specific operations after the framework has registered with the power framework.


## -prototype


````
EVT_WDFDEVICE_WDM_POST_PO_FX_REGISTER_DEVICE EvtDeviceWdmPostPoFxRegisterDevice;

NTSTATUS EvtDeviceWdmPostPoFxRegisterDevice(
  _In_ WDFDEVICE Device,
  _In_ POHANDLE  PoHandle
)
{ ... }
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param PoHandle [in]

A handle that represents the device’s registration with the power framework.


## -returns



An NTSTATUS value indicating success or failure of the operations performed in this callback. If failure is returned, the framework in turn  will fail <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a>.




## -remarks



If you are writing a KMDF driver for a single-component device that defines multiple functional power states, you can register an <i>EvtDeviceWdmPostPoFxRegisterDevice</i> callback function to receive notification after the framework registers with the power management framework (PoFx).

To register <i>EvtDeviceWdmPostPoFxRegisterDevice</i>, a driver must call <a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmassignpowerframeworksettings.md">WdfDeviceWdmAssignPowerFrameworkSettings</a>.

The POHANDLE received in <i>EvtDeviceWdmPostPoFxRegisterDevice</i> remains valid until the driver returns from <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_pre_po_fx_unregister_device.md">EvtDeviceWdmPrePoFxUnregisterDevice</a>.

Your driver can use the POHANDLE to call <a href="..\wdm\nf-wdm-pofxsetcomponentlatency.md">PoFxSetComponentLatency</a>, <a href="..\wdm\nf-wdm-pofxsetcomponentresidency.md">PoFxSetComponentResidency</a>, and <a href="..\wdm\nf-wdm-pofxsetcomponentwake.md">PoFxSetComponentWake</a> to specify latency, residency, and wake hints to the power framework.

 

Your driver can also use the POHANDLE to call <a href="..\wdm\nf-wdm-pofxpowercontrol.md">PoFxPowerControl</a> to send a power control request to PoFx.

A KMDF driver for a multiple component device does not provide <i>EvtDeviceWdmPostPoFxRegisterDevice</i>. Instead, such a driver receives the POHANDLE when it calls <i>PoFxRegisterDevice</i>.  For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-multiple-functional-power-states-for-multiple-component-devices">Supporting Multiple Functional Power States for Multiple-Component Devices</a>.


#### Examples

To define an <i>EvtDeviceWdmPostPoFxRegisterDevice</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceWdmPostPoFxRegisterDevice</i> callback function that is named <i>MyDeviceWdmPostPoFxRegisterDevice</i>, use the <b>EVT_WDFDEVICE_WDM_POST_PO_FX_REGISTER_DEVICE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDFDEVICE_WDM_POST_PO_FX_REGISTER_DEVICE  MyDeviceWdmPostPoFxRegisterDevice;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyDeviceWdmPostPoFxRegisterDevice (
   WDFDEVICE Device,
   POHANDLE PoHandle
   );
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDFDEVICE_WDM_POST_PO_FX_REGISTER_DEVICE</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDFDEVICE_WDM_POST_PO_FX_REGISTER_DEVICE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also

<a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_pre_po_fx_unregister_device.md">EvtDeviceWdmPrePoFxUnregisterDevice</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmassignpowerframeworksettings.md">WdfDeviceWdmAssignPowerFrameworkSettings</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDFDEVICE_WDM_POST_PO_FX_REGISTER_DEVICE callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

