---
UID: NF:wdfdevice.WdfDeviceInitAssignWdmIrpPreprocessCallback
title: WdfDeviceInitAssignWdmIrpPreprocessCallback function
author: windows-driver-content
description: The WdfDeviceInitAssignWdmIrpPreprocessCallback method registers a callback function to handle an IRP major function code and, optionally, one or more minor function codes that are associated with the major function code.
old-location: wdf\wdfdeviceinitassignwdmirppreprocesscallback.htm
old-project: wdf
ms.assetid: 9c17a5e2-dcf2-493a-9851-11d47adbfc82
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DFDeviceObjectGeneralRef_ff2869f4-a557-4d3a-bd4d-67b8e1720ba9.xml, wdfdevice/WdfDeviceInitAssignWdmIrpPreprocessCallback, PFN_WDFDEVICEINITASSIGNWDMIRPPREPROCESSCALLBACK, WdfDeviceInitAssignWdmIrpPreprocessCallback method, kmdf.wdfdeviceinitassignwdmirppreprocesscallback, WdfDeviceInitAssignWdmIrpPreprocessCallback, wdf.wdfdeviceinitassignwdmirppreprocesscallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: ChildDeviceInitAPI, ControlDeviceInitAPI, DeviceInitAPI, DriverCreate, InitFreeDeviceCallback, InitFreeDeviceCreate, InitFreeNull, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI, PdoInitFreeDeviceCallback, PdoInitFreeDeviceCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname: 
-	WdfDeviceInitAssignWdmIrpPreprocessCallback
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceInitAssignWdmIrpPreprocessCallback function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceInitAssignWdmIrpPreprocessCallback</b> method registers a callback function to handle an IRP major function code and, optionally, one or more minor function codes that are associated with the major function code. 


## -syntax


````
NTSTATUS WdfDeviceInitAssignWdmIrpPreprocessCallback(
  _In_     PWDFDEVICE_INIT                  DeviceInit,
  _In_     PFN_WDFDEVICE_WDM_IRP_PREPROCESS EvtDeviceWdmIrpPreprocess,
  _In_     UCHAR                            MajorFunction,
  _In_opt_ PUCHAR                           MinorFunctions,
  _In_     ULONG                            NumMinorFunctions
);
````


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


### -param EvtDeviceWdmIrpPreprocess [in]

A pointer to the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess.md">EvtDeviceWdmIrpPreprocess</a> callback function.


### -param MajorFunction [in]

One of the IRP major function codes that are defined in <i>wdm.h</i>. 


### -param MinorFunctions [in, optional]

A pointer to an array of one or more IRP minor function codes that are associated with the specified major function code. This parameter is optional and can be <b>NULL</b>. For more information, see the following Remarks section.


### -param NumMinorFunctions [in]

The number of minor function codes that are contained in the <i>MinorFunctions</i> array.


## -returns


If the operation succeeds, the method returns STATUS_SUCCESS. Additional return values include:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>MajorFunction</i> value is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There is insufficient memory.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
 The driver previously registered a <i>MinorFunctions</i> array for this major function and is attempting to specify minor functions again for the specified <i>MajorFunction</i> code.

</td>
</tr>
</table> 

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.



## -remarks


Drivers can call the <b>WdfDeviceInitAssignWdmIrpPreprocessCallback</b> method for either of two reasons:
<ul>
<li>
To handle an IRP major or minor function code that the framework does not support. 

For example, the framework does not support <a href="https://msdn.microsoft.com/library/windows/hardware/ff549235">IRP_MJ_FLUSH_BUFFERS</a>. If your driver must support this IRP, it must register an <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess.md">EvtDeviceWdmIrpPreprocess</a> callback function that handles the IRP. The driver must follow WDM rules for processing IRPs.

</li>
<li>
To preprocess an IRP before the framework handles it.

In rare cases, it might be necessary for a driver to process an IRP before the framework processes it. In such cases, the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess.md">EvtDeviceWdmIrpPreprocess</a> callback function can process the IRP and then call <a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmdispatchpreprocessedirp.md">WdfDeviceWdmDispatchPreprocessedIrp</a> to return the IRP to the framework. Depending on the IRP's function code, the framework might process the IRP itself or it might deliver the IRP to the driver again in a framework request object.

</li>
</ul>The framework calls the <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess.md">EvtDeviceWdmIrpPreprocess</a> callback function whenever it receives an I/O request packet (IRP) that contains an IRP major function code that matches the <i>MajorFunction</i> parameter and a minor function code that matches one of the minor function codes that are in the <i>MinorFunctions</i> array. 

If the <i>MinorFunctions</i> array pointer is <b>NULL</b>, the framework calls the callback function for all minor function codes that are associated with the specified major function code. If the <i>MinorFunctions</i> array pointer is not <b>NULL</b>, the framework makes a copy of the array so that the driver does not have to permanently keep its array.

If the driver received <i>DeviceInit</i> pointer from <a href="..\wdfpdo\nf-wdfpdo-wdfpdoinitallocate.md">WdfPdoInitAllocate</a> or an <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_create_device.md">EvtChildListCreateDevice</a> event callback function, the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess.md">EvtDeviceWdmIrpPreprocess</a> callback function cannot set a completion routine for IRPs that contain a major function code of IRP_MJ_PNP. Otherwise, <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a> will report an error.

If your driver calls <b>WdfDeviceInitAssignWdmIrpPreprocessCallback</b> one or more times, the framework increments the <b>StackSize</b> member of the driver's WDM <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure one time. As a result, the I/O manager adds an additional <a href="https://msdn.microsoft.com/62c8ee00-c7cb-4aa1-90ab-b8bedbd818ee">I/O stack location</a> to all IRPs  so that the <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess.md">EvtDeviceWdmIrpPreprocess</a> callback function can set an <a href="..\wdm\nc-wdm-io_completion_routine.md">IoCompletion</a> routine. Note that this extra I/O stack location is added to all IRPs, not just the ones that contain an IRP major function code that you specify in a call to <b>WdfDeviceInitAssignWdmIrpPreprocessCallback</b>. Therefore, to avoid unnecessarily increasing your driver's use of  the nonpaged memory pool, you should avoid using <b>WdfDeviceInitAssignWdmIrpPreprocessCallback</b> unless there is no alternative.

If your driver calls <b>WdfDeviceInitAssignWdmIrpPreprocessCallback</b> more than once for the same major code, the framework retains only the most recently set <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess.md">EvtDeviceWdmIrpPreprocess</a> callback function for this major code.  (Your driver can’t register multiple preprocess callbacks for a single major code.)

For more information about the <b>WdfDeviceInitAssignWdmIrpPreprocessCallback</b> method, see <a href="https://msdn.microsoft.com/43e1df0c-c0d1-4d41-87de-9f8f5831fb19">Handling WDM IRPs Outside of the Framework</a>.



## -see-also

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmdispatchpreprocessedirp.md">WdfDeviceWdmDispatchPreprocessedIrp</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceInitAssignWdmIrpPreprocessCallback method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

