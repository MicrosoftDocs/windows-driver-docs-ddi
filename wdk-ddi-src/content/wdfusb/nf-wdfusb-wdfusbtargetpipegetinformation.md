---
UID: NF:wdfusb.WdfUsbTargetPipeGetInformation
title: WdfUsbTargetPipeGetInformation function
author: windows-driver-content
description: The WdfUsbTargetPipeGetInformation method retrieves information about a USB pipe and its endpoint.
old-location: wdf\wdfusbtargetpipegetinformation.htm
old-project: wdf
ms.assetid: d453cc6a-d81f-485c-a71e-d99c080bfa28
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFUsbRef_edde1f49-9228-48fc-8812-ebfe65f48b18.xml, WdfUsbTargetPipeGetInformation, WdfUsbTargetPipeGetInformation method, kmdf.wdfusbtargetpipegetinformation, wdf.wdfusbtargetpipegetinformation, wdfusb/WdfUsbTargetPipeGetInformation
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
-	WdfUsbTargetPipeGetInformation
product: Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetPipeGetInformation function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetPipeGetInformation</b> method retrieves information about a USB pipe and its endpoint.


## -parameters




### -param Pipe [in]

A handle to a framework pipe object that was obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550057">WdfUsbInterfaceGetConfiguredPipe</a>. 


### -param PipeInformation [out]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff553037">WDF_USB_PIPE_INFORMATION</a> structure that receives information about the pipe and endpoint. 


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



For more information about the <b>WdfUsbTargetPipeGetInformation</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553037">WDF_USB_PIPE_INFORMATION</a> structure and calls <b>WdfUsbTargetPipeGetInformation</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_USB_PIPE_INFORMATION pipeInfo;

WDF_USB_PIPE_INFORMATION_INIT(&amp;pipeInfo);
WdfUsbTargetPipeGetInformation(
                               Pipe,
                               &amp;pipeInfo
                               );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553037">WDF_USB_PIPE_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553040">WDF_USB_PIPE_INFORMATION_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550057">WdfUsbInterfaceGetConfiguredPipe</a>
 

 

