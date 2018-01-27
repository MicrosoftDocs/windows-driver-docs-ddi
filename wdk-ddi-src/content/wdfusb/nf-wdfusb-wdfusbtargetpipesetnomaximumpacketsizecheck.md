---
UID: NF:wdfusb.WdfUsbTargetPipeSetNoMaximumPacketSizeCheck
title: WdfUsbTargetPipeSetNoMaximumPacketSizeCheck function
author: windows-driver-content
description: The WdfUsbTargetPipeSetNoMaximumPacketSizeCheck method disables the framework's test of whether the size of a driver's read buffer is a multiple of a USB pipe's maximum packet size.
old-location: wdf\wdfusbtargetpipesetnomaximumpacketsizecheck.htm
old-project: wdf
ms.assetid: 552eaf46-1710-4df5-bdc3-0fa7ce3adf54
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.wdfusbtargetpipesetnomaximumpacketsizecheck, kmdf.wdfusbtargetpipesetnomaximumpacketsizecheck, wdfusb/WdfUsbTargetPipeSetNoMaximumPacketSizeCheck, WdfUsbTargetPipeSetNoMaximumPacketSizeCheck, DFUsbRef_e750d0d1-6d91-498d-8bb5-2eb9bab0149d.xml, PFN_WDFUSBTARGETPIPESETNOMAXIMUMPACKETSIZECHECK, WdfUsbTargetPipeSetNoMaximumPacketSizeCheck method
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
req.irql: <=DISPATCH_LEVEL
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
-	WdfUsbTargetPipeSetNoMaximumPacketSizeCheck
product: Windows
targetos: Windows
req.typenames: *PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfUsbTargetPipeSetNoMaximumPacketSizeCheck function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetPipeSetNoMaximumPacketSizeCheck</b> method disables the framework's test of whether the size of a driver's read buffer is a multiple of a USB pipe's maximum packet size.


## -syntax


````
VOID WdfUsbTargetPipeSetNoMaximumPacketSizeCheck(
  _In_ WDFUSBPIPE Pipe
);
````


## -parameters




### -param Pipe [in]

A handle to a framework pipe object that was obtained by calling <a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetconfiguredpipe.md">WdfUsbInterfaceGetConfiguredPipe</a>. 


## -returns


None.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


To avoid receiving extra data from unexpected bus activity, which is sometimes called <i>babble</i>, drivers usually specify read buffers that are a multiple of the pipe's maximum packet size. (Drivers receive a USB pipe's maximum packet size in a <a href="..\wdfusb\ns-wdfusb-_wdf_usb_pipe_information.md">WDF_USB_PIPE_INFORMATION</a> structure.) By default, the framework reports an error if a driver specifies a read buffer that is not a multiple of the pipe's maximum packet size. If the driver calls <b>WdfUsbTargetPipeSetNoMaximumPacketSizeCheck</b>, the framework does not report an error if a read buffer is not a multiple of the maximum packet size.

For more information about the <b>WdfUsbTargetPipeSetNoMaximumPacketSizeCheck</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.



## -see-also

<a href="..\wdfusb\ns-wdfusb-_wdf_usb_pipe_information.md">WDF_USB_PIPE_INFORMATION</a>

<a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetconfiguredpipe.md">WdfUsbInterfaceGetConfiguredPipe</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetPipeSetNoMaximumPacketSizeCheck method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

