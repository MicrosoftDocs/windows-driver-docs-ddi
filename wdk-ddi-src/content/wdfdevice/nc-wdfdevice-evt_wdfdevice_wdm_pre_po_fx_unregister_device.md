---
UID: NC:wdfdevice.EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE
title: EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE (wdfdevice.h)
description: The EvtDeviceWdmPrePoFxUnregisterDevice callback function performs device-specific operations before the framework deletes a specified registration with the power framework.
old-location: wdf\evtdevicewdmprepofxunregisterdevice.htm
tech.root: wdf
ms.assetid: D663C47D-C59E-4210-84D8-9773A3003990
ms.date: 02/26/2018
ms.keywords: EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE, EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE callback, EvtDeviceWdmPrePoFxUnregisterDevice, EvtDeviceWdmPrePoFxUnregisterDevice callback function, kmdf.evtdevicewdmprepofxunregisterdevice, wdf.evtdevicewdmprepofxunregisterdevice, wdfdevice/EvtDeviceWdmPrePoFxUnregisterDevice
ms.topic: callback
f1_keywords:
 - "wdfdevice/EvtDeviceWdmPrePoFxUnregisterDevice"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfdevice.h
api_name:
- EvtDeviceWdmPrePoFxUnregisterDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>


   The 
  <i>EvtDeviceWdmPrePoFxUnregisterDevice</i> callback function performs device-specific operations before the framework deletes a specified registration with the power framework.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param PoHandle [in]

A handle that represents the device’s registration with the power framework.


## -returns



This callback function does not return a value.




## -remarks



The <i>EvtDeviceWdmPrePoFxUnregisterDevice</i> callback function applies only to single-component devices.

To register an <i>EvtDeviceWdmPrePoFxUnregisterDevice</i> callback function, a driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmassignpowerframeworksettings">WdfDeviceWdmAssignPowerFrameworkSettings</a>.

A driver can provide this callback function if it must perform any additional operations before the framework unregisters the specified POHANDLE.

 After the driver has returned from this callback, it is no longer safe to use this POHANDLE.


#### Examples

To define an <i>EvtDeviceWdmPrePoFxUnregisterDevice</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceWdmPrePoFxUnregisterDevice</i> callback function that is named <i>MyDeviceWdmPrePoFxUnregisterDevice</i>, use the <b>EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE  MyDeviceWdmPrePoFxUnregisterDevice;</pre>
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
 MyDeviceWdmPrePoFxUnregisterDevice (
   WDFDEVICE Device,
   POHANDLE PoHandle
   );
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_post_po_fx_register_device">EvtDeviceWdmPostPoFxRegisterDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmassignpowerframeworksettings">WdfDeviceWdmAssignPowerFrameworkSettings</a>
 

 

