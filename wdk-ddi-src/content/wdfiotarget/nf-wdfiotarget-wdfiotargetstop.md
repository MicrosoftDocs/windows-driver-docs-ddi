---
UID: NF:wdfiotarget.WdfIoTargetStop
title: WdfIoTargetStop function (wdfiotarget.h)
description: The WdfIoTargetStop method stops sending queued requests to a local or remote I/O target.
old-location: wdf\wdfiotargetstop.htm
tech.root: wdf
ms.assetid: 3dd5aa58-e5a6-4ee3-9b88-d9cbb7eb558c
ms.date: 02/26/2018
keywords: ["WdfIoTargetStop function"]
ms.keywords: DFIOTargetRef_80727681-b08c-4025-aea9-d469735ea00c.xml, WdfIoTargetStop, WdfIoTargetStop method, kmdf.wdfiotargetstop, wdf.wdfiotargetstop, wdfiotarget/WdfIoTargetStop
f1_keywords:
 - "wdfiotarget/WdfIoTargetStop"
 - "WdfIoTargetStop"
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, FailD0EntryIoTargetState, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: See Remarks section.
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
- WdfIoTargetStop
targetos: Windows
req.typenames: 
---

# WdfIoTargetStop function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfIoTargetStop</b> method stops sending queued requests to a local or remote I/O target.


## -parameters




### -param IoTarget [in]

A handle to a local or remote I/O target object that was obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetiotarget">WdfDeviceGetIoTarget</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcreate">WdfIoTargetCreate</a>, or from a method that a specialized I/O target supplies.


### -param Action [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ne-wdfiotarget-_wdf_io_target_sent_io_action">WDF_IO_TARGET_SENT_IO_ACTION</a>-typed value that specifies how the framework should handle I/O requests that the driver has sent to the I/O target, if the target has not completed the requests.


## -remarks

A bug check occurs if the driver supplies an invalid object handle.



If your driver can detect recoverable device errors, you might want your driver to call <b>WdfIoTargetStop</b> to temporarily stop sending requests, then later call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetstart">WdfIoTargetStart</a> to resume sending requests.

While stopped, an I/O target continues to accept new requests but does not deliver the queued requests to the appropriate driver.

For more information about possible states for I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/controlling-a-general-i-o-target-s-state">Controlling a General I/O Target's State</a>.

If a driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetpipeconfigcontinuousreader">WdfUsbTargetPipeConfigContinuousReader</a> to configure a continuous reader for a USB pipe, the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_exit">EvtDeviceD0Exit</a> callback function must call <b>WdfIoTargetStop</b> to stop the reader.

If a driver has called <b>WdfIoTargetStop</b>, it can still send a request to the target by setting the <b>WDF_REQUEST_OPTION_IGNORE_TARGET_STATE</b> flag in the request's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure. If a driver sets this flag, the driver can send a request, such as a request to reset a USB pipe (see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetpiperesetsynchronously">WdfUsbTargetPipeResetSynchronously</a>), to a device after the driver has called <b>WdfIoTargetStop</b>.

When a driver calls <b>WdfIoTargetStop</b>, the framework does not attempt to cancel or wait for I/O requests that were previously sent to the target using either the <b>WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE</b> flag or the <b>WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET</b> flag in the request's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure.

Your driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetstart">WdfIoTargetStart</a> and <b>WdfIoTargetStop</b> synchronously. After the driver calls one of these functions, it must not call either function before the first call returns.

Your driver can call <b>WdfIoTargetStop</b> multiple times from a single thread without calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetstart">WdfIoTargetStart</a>. For example, your driver might do the following:

<ol>
<li>
Call <b>WdfIoTargetStop</b> and specify an <i>Action</i> value of <b>WdfIoTargetLeaveSentIoPending</b>. 

</li>
<li>
Determine whether the target should resume processing I/O requests. 

</li>
<li>
If the target should resume, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetstart">WdfIoTargetStart</a>. Otherwise, call <b>WdfIoTargetStop</b> again with an <i>Action</i> value of <b>WdfIoTargetCancelSentIo</b>. 

</li>
</ol>
<div class="alert"><b>Note</b>  It is not safe to call <b>WdfIoTargetStop</b> multiple times from different threads.</div>
<div> </div>
For more information about I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-i-o-targets">Using I/O Targets</a>.

If the driver has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetpipeconfigcontinuousreader">WdfUsbTargetPipeConfigContinuousReader</a> for the pipe, <b>WdfIoTargetStop</b> must be called at IRQL = PASSIVE_LEVEL.

If the driver has not called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetpipeconfigcontinuousreader">WdfUsbTargetPipeConfigContinuousReader</a> and if the <i>Action</i> parameter of <b>WdfIoTargetStop</b> is <b>WdfIoTargetLeaveSentIoPending</b>, <b>WdfIoTargetStop</b> can be called at IRQL <= DISPATCH_LEVEL. Otherwise, <b>WdfIoTargetStop</b> is called at IRQL = PASSIVE_LEVEL. 


#### Examples

The following code example shows how an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_exit">EvtDeviceD0Exit</a> callback function can call <b>WdfIoTargetStop</b>, if the driver uses a continuous reader for a USB pipe. 

```cpp
NTSTATUS
MyEvtDeviceD0Exit(
    IN  WDFDEVICE Device,
    IN  WDF_POWER_DEVICE_STATE TargetState
)
{
    PDEVICE_CONTEXT  pDeviceContext;
    pDeviceContext = GetMyDeviceContext(Device);

    WdfIoTargetStop(
                    WdfUsbTargetPipeGetIoTarget(pDeviceContext->InterruptPipe),
                    WdfIoTargetCancelSentIo
                    );

    return STATUS_SUCCESS;
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_exit">EvtDeviceD0Exit</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetiotarget">WdfDeviceGetIoTarget</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcreate">WdfIoTargetCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetstart">WdfIoTargetStart</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetpipeconfigcontinuousreader">WdfUsbTargetPipeConfigContinuousReader</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetpiperesetsynchronously">WdfUsbTargetPipeResetSynchronously</a>
 

 

