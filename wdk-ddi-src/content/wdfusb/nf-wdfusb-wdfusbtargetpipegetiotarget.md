---
UID: NF:wdfusb.WdfUsbTargetPipeGetIoTarget
title: WdfUsbTargetPipeGetIoTarget function
author: windows-driver-content
description: The WdfUsbTargetPipeGetIoTarget method returns a handle to the I/O target object that is associated with a specified USB pipe.
old-location: wdf\wdfusbtargetpipegetiotarget.htm
tech.root: wdf
ms.assetid: 73835623-fa35-46f0-90a2-62d6d596dc64
ms.date: 02/26/2018
ms.keywords: DFUsbRef_87bfc4fc-266b-44ca-911f-fc5d73735a6a.xml, WdfUsbTargetPipeGetIoTarget, WdfUsbTargetPipeGetIoTarget method, kmdf.wdfusbtargetpipegetiotarget, wdf.wdfusbtargetpipegetiotarget, wdfusb/WdfUsbTargetPipeGetIoTarget
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, FailD0EntryIoTargetState
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: Any level
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
-	WdfUsbTargetPipeGetIoTarget
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetPipeGetIoTarget function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbTargetPipeGetIoTarget</b> method returns a handle to the I/O target object that is associated with a specified USB pipe.


## -parameters




### -param Pipe [in]

A handle to a framework pipe object that was obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550057">WdfUsbInterfaceGetConfiguredPipe</a>.


## -returns



<b>WdfUsbTargetPipeGetIoTarget</b> returns a handle to the I/O target object that is associated with the specified pipe object.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



For more information about the <b>WdfUsbTargetPipeGetIoTarget</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example shows how an <a href="https://msdn.microsoft.com/0cfabb0f-2d5e-4445-8683-d2916de5b549">EvtDeviceD0Entry</a> callback function can start a continuous reader for a USB pipe. 

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550057">WdfUsbInterfaceGetConfiguredPipe</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550093">WdfUsbTargetDeviceGetIoTarget</a>
 

 

