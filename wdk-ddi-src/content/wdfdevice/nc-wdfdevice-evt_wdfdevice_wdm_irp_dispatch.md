---
UID: NC:wdfdevice.EVT_WDFDEVICE_WDM_IRP_DISPATCH
title: EVT_WDFDEVICE_WDM_IRP_DISPATCH (wdfdevice.h)
description: A driver's EvtDeviceWdmIrpDispatch event callback function receives an IRP before the framework processes the IRP.
old-location: wdf\evtdevicewdmirpdispatch.htm
tech.root: wdf
ms.assetid: C6BED59F-066E-42F6-86AE-B0423E0E847F
ms.date: 02/26/2018
keywords: ["EVT_WDFDEVICE_WDM_IRP_DISPATCH callback function"]
ms.keywords: EVT_WDFDEVICE_WDM_IRP_DISPATCH, EVT_WDFDEVICE_WDM_IRP_DISPATCH callback, EvtDeviceWdmIrpDispatch, EvtDeviceWdmIrpDispatch callback function, kmdf.evtdevicewdmirpdispatch, wdf.evtdevicewdmirpdispatch, wdfdevice/EvtDeviceWdmIrpDispatch
f1_keywords:
 - "wdfdevice/EvtDeviceWdmIrpDispatch"
 - "EvtDeviceWdmIrpDispatch"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 2.17
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfdevice.h
api_name:
- EvtDeviceWdmIrpDispatch
targetos: Windows
req.typenames: 
---

# EVT_WDFDEVICE_WDM_IRP_DISPATCH callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceWdmIrpDispatch</i> event callback function receives an IRP before the framework processes the IRP.


## -parameters




### -param Device 
[in]
A handle to a framework device object.


### -param MajorFunction 
[in]
One of the IRP major function codes that are defined in wdm.h.


### -param MinorFunction 
[in]
One of the I/O IRP minor function codes that are defined in wdm.h for the <i>MajorFunction</i> code.


### -param Code 
[in]
Specifies an I/O control code value.  This parameter is valid only if <i>MajorFunction</i> is set to IRP_MJ_DEVICE_CONTROL.


### -param DriverContext 
[in]
An untyped pointer to driver-defined context information that the driver provided when it called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceconfigurewdmirpdispatchcallback">WdfDeviceConfigureWdmIrpDispatchCallback</a>.


### -param Irp 
[in, out]
A pointer to an IRP structure.


### -param DispatchContext 
[in]
An untyped pointer to the framework's dispatch  context information. The driver must provide this parameter when it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmdispatchirp">WdfDeviceWdmDispatchIrp</a>.


## -returns



The <i>EvtDeviceWdmIrpDispatch</i> callback function must:

<ul>
<li>Return the value that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmdispatchirp">WdfDeviceWdmDispatchIrp</a> method returns, if the callback function calls that method.</li>
<li>Return the value that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmdispatchirptoioqueue">WdfDeviceWdmDispatchIrpToIoQueue</a> method returns, if the callback function calls that method.</li>
<li>
<b>KMDF only</b></p> Set the <b>IoStatus.Status</b> member of the IRP to STATUS_SUCCESS or another status value for which NT_SUCCESS(status) equals TRUE, and return the same value (after calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocompleterequest">IoCompleteRequest</a>) if the callback function successfully completes the received IRP.</li>
<li>
<b>KMDF only</b></p>Set the <b>IoStatus.Status</b> member of the IRP to a status value for which NT_SUCCESS(status) equals FALSE, and return the same value (after calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocompleterequest">IoCompleteRequest</a>) if the callback function detects an error.</li>
<li>
<b>KMDF only</b></p>Return STATUS_PENDING if the callback function calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iomarkirppending">IoMarkIrpPending</a>.</li>
</ul>



## -remarks



The <i>EvtDeviceWdmIrpDispatch</i> callback function should only be used to select a specific queue for an IRP. To do so, the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmdispatchirptoioqueue">WdfDeviceWdmDispatchIrpToIoQueue</a> method from within the callback function.

If, after examining an IRP in this callback function, the driver does not  know how to dispatch the IRP, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmdispatchirp">WdfDeviceWdmDispatchIrp</a> to return the IRP to the framework for default handling.

A UMDF driver must call either <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmdispatchirp">WdfDeviceWdmDispatchIrp</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmdispatchirptoioqueue">WdfDeviceWdmDispatchIrpToIoQueue</a> from this callback function.  A KMDF driver has the additional option of calling neither, and instead completing the IRP or marking it pending.

To register an <i>EvtDeviceWdmIrpDispatch</i> callback function, your driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceconfigurewdmirpdispatchcallback">WdfDeviceConfigureWdmIrpDispatchCallback</a>.

In its <i>EvtDeviceWdmIrpDispatch</i> callback function, a driver should not set a completion routine. If a completion routine is needed, a KMDF driver can provide a  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess">EvtDeviceWdmIrpPreprocess</a> callback function instead of <i>EvtDeviceWdmIrpDispatch</i>.

 For more information about specifying queues for IRPs as they arrive, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dispatching-irps-to-i-o-queues">Dispatching IRPs to I/O Queues</a>.





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceconfigurewdmirpdispatchcallback">WdfDeviceConfigureWdmIrpDispatchCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmdispatchirp">WdfDeviceWdmDispatchIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmdispatchirptoioqueue">WdfDeviceWdmDispatchIrpToIoQueue</a>
 

 

