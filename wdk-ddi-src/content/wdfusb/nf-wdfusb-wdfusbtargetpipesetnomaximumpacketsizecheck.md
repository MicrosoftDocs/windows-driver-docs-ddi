---
UID: NF:wdfusb.WdfUsbTargetPipeSetNoMaximumPacketSizeCheck
title: WdfUsbTargetPipeSetNoMaximumPacketSizeCheck function (wdfusb.h)
description: The WdfUsbTargetPipeSetNoMaximumPacketSizeCheck method disables the framework's test of whether the size of a driver's read buffer is a multiple of a USB pipe's maximum packet size.
old-location: wdf\wdfusbtargetpipesetnomaximumpacketsizecheck.htm
tech.root: wdf
ms.assetid: 552eaf46-1710-4df5-bdc3-0fa7ce3adf54
ms.date: 02/26/2018
ms.keywords: DFUsbRef_e750d0d1-6d91-498d-8bb5-2eb9bab0149d.xml, WdfUsbTargetPipeSetNoMaximumPacketSizeCheck, WdfUsbTargetPipeSetNoMaximumPacketSizeCheck method, kmdf.wdfusbtargetpipesetnomaximumpacketsizecheck, wdf.wdfusbtargetpipesetnomaximumpacketsizecheck, wdfusb/WdfUsbTargetPipeSetNoMaximumPacketSizeCheck
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
- WdfUsbTargetPipeSetNoMaximumPacketSizeCheck
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetPipeSetNoMaximumPacketSizeCheck function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbTargetPipeSetNoMaximumPacketSizeCheck</b> method disables the framework's test of whether the size of a driver's read buffer is a multiple of a USB pipe's maximum packet size.


## -parameters




### -param Pipe [in]

A handle to a framework pipe object that was obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550057">WdfUsbInterfaceGetConfiguredPipe</a>. 


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



To avoid receiving extra data from unexpected bus activity, which is sometimes called <i>babble</i>, drivers usually specify read buffers that are a multiple of the pipe's maximum packet size. (Drivers receive a USB pipe's maximum packet size in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553037">WDF_USB_PIPE_INFORMATION</a> structure.) By default, the framework reports an error if a driver specifies a read buffer that is not a multiple of the pipe's maximum packet size. If the driver calls <b>WdfUsbTargetPipeSetNoMaximumPacketSizeCheck</b>, the framework does not report an error if a read buffer is not a multiple of the maximum packet size.

For more information about the <b>WdfUsbTargetPipeSetNoMaximumPacketSizeCheck</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example disables the framework's test of whether the size of a buffer is a multiple of a USB pipe's maximum packet size.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfUsbTargetPipeSetNoMaximumPacketSizeCheck(pipe);
 </pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553037">WDF_USB_PIPE_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550057">WdfUsbInterfaceGetConfiguredPipe</a>
 

 

