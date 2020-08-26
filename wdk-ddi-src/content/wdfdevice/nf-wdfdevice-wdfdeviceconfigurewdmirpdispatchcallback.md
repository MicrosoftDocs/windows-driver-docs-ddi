---
UID: NF:wdfdevice.WdfDeviceConfigureWdmIrpDispatchCallback
title: WdfDeviceConfigureWdmIrpDispatchCallback function (wdfdevice.h)
description: The WdfDeviceConfigureWdmIrpDispatchCallback method registers a driver's EvtDeviceWdmIrpDispatch callback function.
old-location: wdf\wdfdeviceconfigurewdmirpdispatchcallback.htm
tech.root: wdf
ms.assetid: 594E0FF1-A965-4CE4-A2EA-C9098685FCED
ms.date: 02/26/2018
keywords: ["WdfDeviceConfigureWdmIrpDispatchCallback function"]
ms.keywords: WdfDeviceConfigureWdmIrpDispatchCallback, WdfDeviceConfigureWdmIrpDispatchCallback method, kmdf.wdfdeviceconfigurewdmirpdispatchcallback, wdf.wdfdeviceconfigurewdmirpdispatchcallback, wdfdevice/WdfDeviceConfigureWdmIrpDispatchCallback
f1_keywords:
 - "wdfdevice/WdfDeviceConfigureWdmIrpDispatchCallback"
 - "WdfDeviceConfigureWdmIrpDispatchCallback"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 2.17
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfDeviceConfigureWdmIrpDispatchCallback
targetos: Windows
req.typenames: 
---

# WdfDeviceConfigureWdmIrpDispatchCallback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceConfigureWdmIrpDispatchCallback</b> method registers a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_irp_dispatch">EvtDeviceWdmIrpDispatch</a> callback function.


## -parameters




### -param Device 
[in]
A handle to a framework device object.


### -param Driver 
[in, optional]
A handle to the driver's framework driver object that the driver obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfdrivercreate">WdfDriverCreate</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nf-wdfdriver-wdfgetdriver">WdfGetDriver</a>.  This parameter is optional.


### -param MajorFunction 
[in]
One of the following IRP major function codes: IRP_MJ_DEVICE_CONTROL, IRP_MJ_INTERNAL_DEVICE_CONTROL, IRP_MJ_READ, IRP_MJ_WRITE.


### -param EvtDeviceWdmIrpDisptach

<p>A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_irp_dispatch"><i>EvtDeviceWdmIrpDispatch</i></a> callback function.</p>


### -param DriverContext 
[in, optional]
An untyped pointer to driver-defined context information that the framework passes to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_irp_dispatch">EvtDeviceWdmIrpDispatch</a> callback function. This parameter is optional and can be NULL.


## -returns



If the <b>WdfDeviceConfigureWdmIrpDispatchCallback</b> method encounters no errors, it returns STATUS_SUCCESS. Additional return values include:

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
An invalid <i>MajorFunction</i> value was supplied.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Insufficient memory was available.

</td>
</tr>
</table>
 




## -remarks



A driver calls the <b>WdfDeviceConfigureWdmIrpDispatchCallback</b> method to register an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_irp_dispatch">EvtDeviceWdmIrpDispatch</a> callback function. The framework then calls <i>EvtDeviceWdmIrpDispatch</i> whenever it receives an I/O request packet (IRP) containing an IRP major function code that matches the <i>MajorFunction</i> parameter of this method.

A driver typically calls <b>WdfDeviceConfigureWdmIrpDispatchCallback</b> from its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function.

You must call <b>WdfDeviceConfigureWdmIrpDispatchCallback</b> once for each MJ function for which the driver wants to register a callback function. In other words, multiple calls are required for intercepting multiple MJ functions.

A driver might call the <b>WdfDeviceConfigureWdmIrpDispatchCallback</b> method for these reasons:<ul>
<li>To examine an IRP and assign it to  a specific queue based on domain-specific criteria, for example, direct all I/O associated with a file object to a particular queue.</li>
<li>To select on an individual request basis the need to call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_io_in_caller_context">EvtIoInCallerContext</a> callback function.</li>
</ul>


 For more information about specifying queues for IRPs as they arrive, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dispatching-irps-to-i-o-queues">Dispatching IRPs to I/O Queues</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_irp_dispatch">EvtDeviceWdmIrpDispatch</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmdispatchirp">WdfDeviceWdmDispatchIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmdispatchirptoioqueue">WdfDeviceWdmDispatchIrpToIoQueue</a>
 

 

