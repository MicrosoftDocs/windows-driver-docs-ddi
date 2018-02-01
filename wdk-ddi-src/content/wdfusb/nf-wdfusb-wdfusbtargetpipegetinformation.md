---
UID: NF:wdfusb.WdfUsbTargetPipeGetInformation
title: WdfUsbTargetPipeGetInformation function
author: windows-driver-content
description: The WdfUsbTargetPipeGetInformation method retrieves information about a USB pipe and its endpoint.
old-location: wdf\wdfusbtargetpipegetinformation.htm
old-project: wdf
ms.assetid: d453cc6a-d81f-485c-a71e-d99c080bfa28
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfusb/WdfUsbTargetPipeGetInformation, kmdf.wdfusbtargetpipegetinformation, DFUsbRef_edde1f49-9228-48fc-8812-ebfe65f48b18.xml, wdf.wdfusbtargetpipegetinformation, WdfUsbTargetPipeGetInformation, PFN_WDFUSBTARGETPIPEGETINFORMATION, WdfUsbTargetPipeGetInformation method
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
-	WdfUsbTargetPipeGetInformation
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfUsbTargetPipeGetInformation function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetPipeGetInformation</b> method retrieves information about a USB pipe and its endpoint.


## -syntax


````
VOID WdfUsbTargetPipeGetInformation(
  _In_  WDFUSBPIPE                Pipe,
  _Out_ PWDF_USB_PIPE_INFORMATION PipeInformation
);
````


## -parameters




### -param Pipe [in]

A handle to a framework pipe object that was obtained by calling <a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetconfiguredpipe.md">WdfUsbInterfaceGetConfiguredPipe</a>. 


### -param PipeInformation [out]

A pointer to a caller-allocated <a href="..\wdfusb\ns-wdfusb-_wdf_usb_pipe_information.md">WDF_USB_PIPE_INFORMATION</a> structure that receives information about the pipe and endpoint. 


## -returns


None.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


For more information about the <b>WdfUsbTargetPipeGetInformation</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.



## -see-also

<a href="..\wdfusb\nf-wdfusb-wdf_usb_pipe_information_init.md">WDF_USB_PIPE_INFORMATION_INIT</a>

<a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetconfiguredpipe.md">WdfUsbInterfaceGetConfiguredPipe</a>

<a href="..\wdfusb\ns-wdfusb-_wdf_usb_pipe_information.md">WDF_USB_PIPE_INFORMATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetPipeGetInformation method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

