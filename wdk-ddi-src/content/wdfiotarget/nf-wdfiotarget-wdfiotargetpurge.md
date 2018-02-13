---
UID: NF:wdfiotarget.WdfIoTargetPurge
title: WdfIoTargetPurge function
author: windows-driver-content
description: The WdfIoTargetPurge method cancels all I/O requests queued to a local, remote, or specialized I/O target and prevents any new I/O requests from being queued.
old-location: wdf\wdfiotargetpurge.htm
old-project: wdf
ms.assetid: C79492C5-3872-4ED9-9AD7-ABE5C5732D41
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfiotarget/WdfIoTargetPurge, kmdf.wdfiotargetpurge, WdfIoTargetPurge method, WdfIoTargetPurge, wdf.wdfiotargetpurge
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	WdfIoTargetPurge
product: Windows
targetos: Windows
req.typenames: WDF_IO_TARGET_STATE, *PWDF_IO_TARGET_STATE
req.product: Windows 10 or later.
---

# WdfIoTargetPurge function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoTargetPurge</b> method cancels all I/O requests queued to a local, remote, or specialized I/O target and prevents any new I/O requests from being queued. The method also attempts to cancel I/O requests that have left the I/O target's queue and entered lower drivers.


## -syntax


````
VOID WdfIoTargetPurge(
  _In_ WDFIOTARGET                   IoTarget,
  _In_ WDF_IO_TARGET_PURGE_IO_ACTION Action
);
````


## -parameters




### -param IoTarget [in]

A handle to a local or remote I/O target object that was obtained from a previous call to <a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetiotarget.md">WdfDeviceGetIoTarget</a> or <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>, or from a method supplied by a specialized I/O target, such as <a href="..\wdfusb\nf-wdfusb-wdfusbtargetpipegetiotarget.md">WdfUsbTargetPipeGetIoTarget</a>.


### -param Action [in]

A <a href="..\wdfiotarget\ne-wdfiotarget-_wdf_io_target_purge_io_action.md">WDF_IO_TARGET_PURGE_IO_ACTION</a>-typed value that indicates whether the framework should wait to return from  <b>WdfIoTargetPurge</b> until all delivered requests are completed or canceled. 


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



If the driver has previously called <a href="..\wdfusb\nf-wdfusb-wdfusbtargetpipeconfigcontinuousreader.md">WdfUsbTargetPipeConfigContinuousReader</a>, <b>WdfIoTargetPurge</b> must be called at IRQL = PASSIVE_LEVEL. 
If the driver has not called <b>WdfUsbTargetPipeConfigContinuousReader</b> and if the <i>Action</i> parameter of <b>WdfIoTargetPurge</b> is <b>WdfIoTargetPurgeIo</b>, <b>WdfIoTargetPurge</b> can be called at IRQL &lt;= DISPATCH_LEVEL. Otherwise, <b>WdfIoTargetPurge</b> must be called at IRQL = PASSIVE_LEVEL.

To make <b>WdfIoTargetPurge</b> a synchronous call, the driver can set the <b>WdfIoTargetPurgeIoAndWait</b> value of the <i>Action</i> parameter. In this case, <b>WdfIoTargetPurge</b> waits to return until all delivered requests are completed or canceled.

After a driver has called <b>WdfIoTargetPurge</b>, it can still send a request to the target by setting the <b>WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE</b> flag in the request's <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure. For example, a driver might send a request, such as a request to reset a USB pipe (see <a href="..\wdfusb\nf-wdfusb-wdfusbtargetpiperesetsynchronously.md">WdfUsbTargetPipeResetSynchronously</a>), to a device after the driver has called <b>WdfIoTargetPurge</b>.

When a driver calls <b>WdfIoTargetPurge</b>, the framework does not attempt to cancel or wait for I/O requests that were previously sent to the target using either the <b>WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE</b> flag or the <b>WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET</b> flag in the request's <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure.

After a driver has purged an I/O queue, it can restart the queue by calling <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetstart.md">WdfIoTargetStart</a>.

Your driver must call <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetstart.md">WdfIoTargetStart</a>, <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetstop.md">WdfIoTargetStop</a> and <b>WdfIoTargetPurge</b> synchronously. After the driver calls one of these functions, it must not call any of the others until the previous call returns.


Your driver can call <b>WdfIoTargetPurge</b> multiple times without calling <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetstart.md">WdfIoTargetStart</a>. For example, your driver might do the following:
<ol>
<li>Call <b>WdfIoTargetPurge</b> and specify an <i>Action</i> value of <b>WdfIoTargetPurgeIo</b>.</li>
<li>Determine whether the target should resume processing I/O requests.</li>
<li>If the target should resume, call <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetstart.md">WdfIoTargetStart</a>. Otherwise, call <b>WdfIoTargetPurge</b> again with an <i>Action</i> value of <b>WdfIoTargetPurgeIoAndWait</b>. 
</li>
</ol>


For more information about I/O target states, see <a href="https://msdn.microsoft.com/37f756bf-b655-428e-b72c-f86c71f1a2db">Controlling a General I/O Target's State</a>. 

For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.


#### Examples

The following code example shows how an <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_exit.md">EvtDeviceD0Exit</a> callback function can call <b>WdfIoTargetPurge</b>, if the driver uses a continuous reader for a USB pipe.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
MyEvtDeviceD0Exit(
    IN  WDFDEVICE Device,
    IN  WDF_POWER_DEVICE_STATE TargetState
)
{
    PDEVICE_CONTEXT  pDeviceContext;
    pDeviceContext = GetMyDeviceContext(Device);

    WdfIoTargetPurge(
                    WdfUsbTargetPipeGetIoTarget(pDeviceContext-&gt;InterruptPipe),
                    WdfIoTargetPurgeIoAndWait
                    );

    return STATUS_SUCCESS;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetstart.md">WdfIoTargetStart</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetgetstate.md">WdfIoTargetGetState</a>



<a href="..\wdfiotarget\ne-wdfiotarget-_wdf_io_target_purge_io_action.md">WDF_IO_TARGET_PURGE_IO_ACTION</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetstop.md">WdfIoTargetStop</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoTargetPurge method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

