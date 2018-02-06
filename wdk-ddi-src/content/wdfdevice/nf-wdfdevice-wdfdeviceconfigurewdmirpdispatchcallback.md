---
UID: NF:wdfdevice.WdfDeviceConfigureWdmIrpDispatchCallback
title: WdfDeviceConfigureWdmIrpDispatchCallback function
author: windows-driver-content
description: The WdfDeviceConfigureWdmIrpDispatchCallback method registers a driver's EvtDeviceWdmIrpDispatch callback function.
old-location: wdf\wdfdeviceconfigurewdmirpdispatchcallback.htm
old-project: wdf
ms.assetid: 594E0FF1-A965-4CE4-A2EA-C9098685FCED
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: kmdf.wdfdeviceconfigurewdmirpdispatchcallback, wdf.wdfdeviceconfigurewdmirpdispatchcallback, wdfdevice/WdfDeviceConfigureWdmIrpDispatchCallback, WdfDeviceConfigureWdmIrpDispatchCallback, WdfDeviceConfigureWdmIrpDispatchCallback method, PFN_WDFDEVICECONFIGUREWDMIRPDISPATCHCALLBACK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfDeviceConfigureWdmIrpDispatchCallback
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceConfigureWdmIrpDispatchCallback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceConfigureWdmIrpDispatchCallback</b> method registers a driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_irp_dispatch.md">EvtDeviceWdmIrpDispatch</a> callback function.


## -syntax


````
NTSTATUS WdfDeviceConfigureWdmIrpDispatchCallback(
  _In_     WDFDEVICE                      Device,
  _In_opt_ WDFDRIVER                      Driver,
  _In_     UCHAR                          MajorFunction,
  _In_     PFN_WDFDEVICE_WDM_IRP_DISPATCH EvtDeviceWdmIrpDispatch,
  _In_opt_ WDFCONTEXT                     DriverContext
);
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Driver [in, optional]

A handle to the driver's framework driver object that the driver obtained from a previous call to <a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a> or <a href="..\wdfdriver\nf-wdfdriver-wdfgetdriver.md">WdfGetDriver</a>.  This parameter is optional.


### -param MajorFunction [in]

One of the following IRP major function codes: IRP_MJ_DEVICE_CONTROL, IRP_MJ_INTERNAL_DEVICE_CONTROL, IRP_MJ_READ, IRP_MJ_WRITE.


### -param EvtDeviceWdmIrpDisptach

TBD


### -param DriverContext [in, optional]

An untyped pointer to driver-defined context information that the framework passes to the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_irp_dispatch.md">EvtDeviceWdmIrpDispatch</a> callback function. This parameter is optional and can be NULL.


#### - EvtDeviceWdmIrpDispatch [in]

A pointer to the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_irp_dispatch.md">EvtDeviceWdmIrpDispatch</a> callback function.


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


A driver calls the <b>WdfDeviceConfigureWdmIrpDispatchCallback</b> method to register an <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_irp_dispatch.md">EvtDeviceWdmIrpDispatch</a> callback function. The framework then calls <i>EvtDeviceWdmIrpDispatch</i> whenever it receives an I/O request packet (IRP) containing an IRP major function code that matches the <i>MajorFunction</i> parameter of this method.

A driver typically calls <b>WdfDeviceConfigureWdmIrpDispatchCallback</b> from its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function.

You must call <b>WdfDeviceConfigureWdmIrpDispatchCallback</b> once for each MJ function for which the driver wants to register a callback function. In other words, multiple calls are required for intercepting multiple MJ functions.

A driver might call the <b>WdfDeviceConfigureWdmIrpDispatchCallback</b> method for these reasons:<ul>
<li>To examine an IRP and assign it to  a specific queue based on domain-specific criteria, for example, direct all I/O associated with a file object to a particular queue.</li>
<li>To select on an individual request basis the need to call the <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_io_in_caller_context.md">EvtIoInCallerContext</a> callback function.</li>
</ul>


 For more information about specifying queues for IRPs as they arrive, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dispatching-irps-to-i-o-queues">Dispatching IRPs to I/O Queues</a>.



## -see-also

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmdispatchirptoioqueue.md">WdfDeviceWdmDispatchIrpToIoQueue</a>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_irp_dispatch.md">EvtDeviceWdmIrpDispatch</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmdispatchirp.md">WdfDeviceWdmDispatchIrp</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceConfigureWdmIrpDispatchCallback method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

