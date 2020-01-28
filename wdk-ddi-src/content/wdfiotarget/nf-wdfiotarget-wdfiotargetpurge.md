---
UID: NF:wdfiotarget.WdfIoTargetPurge
title: WdfIoTargetPurge function (wdfiotarget.h)
description: The WdfIoTargetPurge method cancels all I/O requests queued to a local, remote, or specialized I/O target and prevents any new I/O requests from being queued.
old-location: wdf\wdfiotargetpurge.htm
tech.root: wdf
ms.assetid: C79492C5-3872-4ED9-9AD7-ABE5C5732D41
ms.date: 02/26/2018
ms.keywords: WdfIoTargetPurge, WdfIoTargetPurge method, kmdf.wdfiotargetpurge, wdf.wdfiotargetpurge, wdfiotarget/WdfIoTargetPurge
f1_keywords:
 - "wdfiotarget/WdfIoTargetPurge"
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate
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
- WdfIoTargetPurge
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoTargetPurge function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfIoTargetPurge</b> method cancels all I/O requests queued to a local, remote, or specialized I/O target and prevents any new I/O requests from being queued. The method also attempts to cancel I/O requests that have left the I/O target's queue and entered lower drivers.


## -parameters




### -param IoTarget [in]

A handle to a local or remote I/O target object that was obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetiotarget">WdfDeviceGetIoTarget</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcreate">WdfIoTargetCreate</a>, or from a method supplied by a specialized I/O target, such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetpipegetiotarget">WdfUsbTargetPipeGetIoTarget</a>.


### -param Action [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ne-wdfiotarget-_wdf_io_target_purge_io_action">WDF_IO_TARGET_PURGE_IO_ACTION</a>-typed value that indicates whether the framework should wait to return from  <b>WdfIoTargetPurge</b> until all delivered requests are completed or canceled. 


## -remarks

A bug check occurs if the driver supplies an invalid object handle.



If the driver has previously called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetpipeconfigcontinuousreader">WdfUsbTargetPipeConfigContinuousReader</a>, <b>WdfIoTargetPurge</b> must be called at IRQL = PASSIVE_LEVEL. 
If the driver has not called <b>WdfUsbTargetPipeConfigContinuousReader</b> and if the <i>Action</i> parameter of <b>WdfIoTargetPurge</b> is <b>WdfIoTargetPurgeIo</b>, <b>WdfIoTargetPurge</b> can be called at IRQL <= DISPATCH_LEVEL. Otherwise, <b>WdfIoTargetPurge</b> must be called at IRQL = PASSIVE_LEVEL.

To make <b>WdfIoTargetPurge</b> a synchronous call, the driver can set the <b>WdfIoTargetPurgeIoAndWait</b> value of the <i>Action</i> parameter. In this case, <b>WdfIoTargetPurge</b> waits to return until all delivered requests are completed or canceled.

After a driver has called <b>WdfIoTargetPurge</b>, it can still send a request to the target by setting the <b>WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE</b> flag in the request's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure. For example, a driver might send a request, such as a request to reset a USB pipe (see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetpiperesetsynchronously">WdfUsbTargetPipeResetSynchronously</a>), to a device after the driver has called <b>WdfIoTargetPurge</b>.

When a driver calls <b>WdfIoTargetPurge</b>, the framework does not attempt to cancel or wait for I/O requests that were previously sent to the target using either the <b>WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE</b> flag or the <b>WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET</b> flag in the request's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure.

After a driver has purged an I/O queue, it can restart the queue by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetstart">WdfIoTargetStart</a>.

Your driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetstart">WdfIoTargetStart</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetstop">WdfIoTargetStop</a> and <b>WdfIoTargetPurge</b> synchronously. After the driver calls one of these functions, it must not call any of the others until the previous call returns.


Your driver can call <b>WdfIoTargetPurge</b> multiple times without calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetstart">WdfIoTargetStart</a>. For example, your driver might do the following:
<ol>
<li>Call <b>WdfIoTargetPurge</b> and specify an <i>Action</i> value of <b>WdfIoTargetPurgeIo</b>.</li>
<li>Determine whether the target should resume processing I/O requests.</li>
<li>If the target should resume, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetstart">WdfIoTargetStart</a>. Otherwise, call <b>WdfIoTargetPurge</b> again with an <i>Action</i> value of <b>WdfIoTargetPurgeIoAndWait</b>. 
</li>
</ol>


For more information about I/O target states, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/controlling-a-general-i-o-target-s-state">Controlling a General I/O Target's State</a>. 

For more information about I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-i-o-targets">Using I/O Targets</a>.


#### Examples

The following code example shows how an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_exit">EvtDeviceD0Exit</a> callback function can call <b>WdfIoTargetPurge</b>, if the driver uses a continuous reader for a USB pipe.

```cpp
NTSTATUS
MyEvtDeviceD0Exit(
    IN  WDFDEVICE Device,
    IN  WDF_POWER_DEVICE_STATE TargetState
)
{
    PDEVICE_CONTEXT  pDeviceContext;
    pDeviceContext = GetMyDeviceContext(Device);

    WdfIoTargetPurge(
                    WdfUsbTargetPipeGetIoTarget(pDeviceContext->InterruptPipe),
                    WdfIoTargetPurgeIoAndWait
                    );

    return STATUS_SUCCESS;
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ne-wdfiotarget-_wdf_io_target_purge_io_action">WDF_IO_TARGET_PURGE_IO_ACTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcreate">WdfIoTargetCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetgetstate">WdfIoTargetGetState</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetstart">WdfIoTargetStart</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetstop">WdfIoTargetStop</a>
 

 

