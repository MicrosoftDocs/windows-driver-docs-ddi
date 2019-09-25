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
f1_keywords:
 - "wdfusb/WdfUsbTargetPipeSetNoMaximumPacketSizeCheck"
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
req.irql: <=DISPATCH_LEVEL
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

A handle to a framework pipe object that was obtained by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbinterfacegetconfiguredpipe">WdfUsbInterfaceGetConfiguredPipe</a>. 


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



To avoid receiving extra data from unexpected bus activity, which is sometimes called <i>babble</i>, drivers usually specify read buffers that are a multiple of the pipe's maximum packet size. (Drivers receive a USB pipe's maximum packet size in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/ns-wdfusb-_wdf_usb_pipe_information">WDF_USB_PIPE_INFORMATION</a> structure.) By default, the framework reports an error if a driver specifies a read buffer that is not a multiple of the pipe's maximum packet size. If the driver calls <b>WdfUsbTargetPipeSetNoMaximumPacketSizeCheck</b>, the framework does not report an error if a read buffer is not a multiple of the maximum packet size.

For more information about the <b>WdfUsbTargetPipeSetNoMaximumPacketSizeCheck</b> method and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.


#### Examples

The following code example disables the framework's test of whether the size of a buffer is a multiple of a USB pipe's maximum packet size.

```cpp
WdfUsbTargetPipeSetNoMaximumPacketSizeCheck(pipe);
 
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/ns-wdfusb-_wdf_usb_pipe_information">WDF_USB_PIPE_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbinterfacegetconfiguredpipe">WdfUsbInterfaceGetConfiguredPipe</a>
 

 

