---
UID: NF:wdfiotarget.WdfIoTargetStart
title: WdfIoTargetStart function
author: windows-driver-content
description: The WdfIoTargetStart method starts sending queued requests to a local or remote I/O target.
old-location: wdf\wdfiotargetstart.htm
tech.root: wdf
ms.assetid: 0d270910-f0ff-4305-bd68-caa36d3a02c5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFIOTargetRef_40667bdf-5de8-4728-9c55-4a88f7a51704.xml, WdfIoTargetStart, WdfIoTargetStart method, kmdf.wdfiotargetstart, wdf.wdfiotargetstart, wdfiotarget/WdfIoTargetStart
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfIoTargetStart
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoTargetStart function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoTargetStart</b> method starts sending queued requests to a local or remote I/O target.


## -parameters




### -param IoTarget [in]

A handle to a local or remote I/O target object that was obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff546017">WdfDeviceGetIoTarget</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548591">WdfIoTargetCreate</a>, or from a method that a specialized I/O target provides.


## -returns



<b>WdfIoTargetStart</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_STATE</b></dt>
</dl>
</td>
<td width="60%">
The device has been removed.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



If your driver can detect recoverable device errors, you might want your driver to call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548680">WdfIoTargetStop</a> to temporarily stop sending requests, then later call <b>WdfIoTargetStart</b> to resume sending requests.

Additionally, if a driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff551130">WdfUsbTargetPipeConfigContinuousReader</a> to configure a continuous reader for a USB pipe, the driver's <a href="https://msdn.microsoft.com/0cfabb0f-2d5e-4445-8683-d2916de5b549">EvtDeviceD0Entry</a> callback function must call <b>WdfIoTargetStart</b> to start the reader.

Your driver must call <b>WdfIoTargetStart</b> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff548680">WdfIoTargetStop</a> synchronously. After the driver calls one of these functions, it must not call the other function before the first one returns.

For more information about <b>WdfIoTargetStart</b>, see <a href="https://msdn.microsoft.com/37f756bf-b655-428e-b72c-f86c71f1a2db">Controlling a General I/O Target's State</a>. 

For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.


#### Examples

The following code example shows how an <a href="https://msdn.microsoft.com/0cfabb0f-2d5e-4445-8683-d2916de5b549">EvtDeviceD0Entry</a> callback function can call <b>WdfIoTargetStart</b>, if the driver uses a continuous reader for a USB pipe. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
MyEvtDeviceD0Entry(
    IN  WDFDEVICE Device,
    IN  WDF_POWER_DEVICE_STATE PreviousState
)
{
    PDEVICE_CONTEXT  pDeviceContext;
    NTSTATUS  status;

    pDeviceContext = GetMyDeviceContext(Device);

    status = WdfIoTargetStart(WdfUsbTargetPipeGetIoTarget(pDeviceContext-&gt;InterruptPipe));

    return status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/0cfabb0f-2d5e-4445-8683-d2916de5b549">EvtDeviceD0Entry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546017">WdfDeviceGetIoTarget</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548591">WdfIoTargetCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548680">WdfIoTargetStop</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551130">WdfUsbTargetPipeConfigContinuousReader</a>
 

 

