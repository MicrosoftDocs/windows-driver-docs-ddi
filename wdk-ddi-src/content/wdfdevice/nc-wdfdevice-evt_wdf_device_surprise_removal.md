---
UID: NC:wdfdevice.EVT_WDF_DEVICE_SURPRISE_REMOVAL
title: EVT_WDF_DEVICE_SURPRISE_REMOVAL (wdfdevice.h)
description: A driver's EvtDeviceSurpriseRemoval event callback function performs any operations that are needed after a device has been unexpectedly removed from the system or after a driver reports that the device has failed.
old-location: wdf\evtdevicesurpriseremoval.htm
tech.root: wdf
ms.assetid: 0fa0eb7e-7fbb-4838-b1d7-ef5a9d5024d4
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_3623a2b6-f452-4e7d-98a3-d9e42d815f35.xml, EVT_WDF_DEVICE_SURPRISE_REMOVAL, EVT_WDF_DEVICE_SURPRISE_REMOVAL callback, EvtDeviceSurpriseRemoval, EvtDeviceSurpriseRemoval callback function, kmdf.evtdevicesurpriseremoval, wdf.evtdevicesurpriseremoval, wdfdevice/EvtDeviceSurpriseRemoval
ms.topic: callback
f1_keywords:
 - "wdfdevice/EvtDeviceSurpriseRemoval"
req.header: wdfdevice.h
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfdevice.h
api_name:
- EvtDeviceSurpriseRemoval
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_SURPRISE_REMOVAL callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceSurpriseRemoval</i> event callback function performs any operations that are needed after a device has been unexpectedly removed from the system or after a driver reports that <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/reporting-device-failures">the device has failed</a>.


## -parameters




### -param Device [in]

A handle to a framework device object.


## -remarks



To register an <i>EvtDeviceSurpriseRemoval</i> callback function, a driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

The framework does not synchronize the <i>EvtDeviceSurpriseRemoval</i> callback function with other PnP and power management callback functions. For information about how the framework synchronizes the execution of a driver's event callback functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-automatic-synchronization">Using Automatic Synchronization</a>. 

For more information about when the framework calls this callback function, and for more information about synchronization issues, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/a-user-unplugs-a-device">A User Unplugs a Device</a>.






#### Examples

To define an <i>EvtDeviceSurpriseRemoval</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceSurpriseRemoval</i> callback function that is named <i>MyDeviceSurpriseRemoval</i>, use the <b>EVT_WDF_DEVICE_SURPRISE_REMOVAL</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_SURPRISE_REMOVAL  MyDeviceSurpriseRemoval;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyDeviceSurpriseRemoval (
    WDFDEVICE  Device
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_SURPRISE_REMOVAL</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_SURPRISE_REMOVAL</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.



