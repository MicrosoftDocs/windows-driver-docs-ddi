---
UID: NF:wdfusb.WdfUsbTargetPipeIsOutEndpoint
title: WdfUsbTargetPipeIsOutEndpoint function
author: windows-driver-content
description: The WdfUsbTargetPipeIsOutEndpoint method determines whether a specified USB pipe is connected to an output endpoint.
old-location: wdf\wdfusbtargetpipeisoutendpoint.htm
old-project: wdf
ms.assetid: 803d282b-f6eb-4cd3-91b3-899f983c9dc5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFUsbRef_19c3e865-4f6c-4950-93af-46a8b97ec6b9.xml, WdfUsbTargetPipeIsOutEndpoint, WdfUsbTargetPipeIsOutEndpoint method, kmdf.wdfusbtargetpipeisoutendpoint, wdf.wdfusbtargetpipeisoutendpoint, wdfusb/WdfUsbTargetPipeIsOutEndpoint
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2
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
-	WdfUsbTargetPipeIsOutEndpoint
product: Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetPipeIsOutEndpoint function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetPipeIsOutEndpoint</b> method determines whether a specified USB pipe is connected to an output endpoint.


## -parameters




### -param Pipe [in]

A handle to a framework pipe object that represents a bulk pipe or interrupt pipe and was obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550057">WdfUsbInterfaceGetConfiguredPipe</a>. 


## -returns



<b>WdfUsbTargetPipeIsOutEndpoint</b> returns <b>TRUE</b> if the pipe that the <i>Pipe</i> handle represents an output endpoint. The method returns <b>FALSE</b> if the endpoint is an input endpoint.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



For more information about the <b>WdfUsbTargetPipeIsOutEndpoint</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example determines whether a specified USB pipe is connected to an output endpoint.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BOOLEAN isOutEndPoint;

isOutEndPoint = WdfUsbTargetPipeIsOutEndpoint(usbPipe);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553032">WDF_USB_PIPE_DIRECTION_OUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550057">WdfUsbInterfaceGetConfiguredPipe</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551151">WdfUsbTargetPipeIsInEndpoint</a>
 

 

