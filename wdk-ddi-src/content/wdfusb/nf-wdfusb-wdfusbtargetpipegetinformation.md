---
UID: NF:wdfusb.WdfUsbTargetPipeGetInformation
title: WdfUsbTargetPipeGetInformation function (wdfusb.h)
description: The WdfUsbTargetPipeGetInformation method retrieves information about a USB pipe and its endpoint.
old-location: wdf\wdfusbtargetpipegetinformation.htm
tech.root: wdf
ms.assetid: d453cc6a-d81f-485c-a71e-d99c080bfa28
ms.date: 02/26/2018
keywords: ["WdfUsbTargetPipeGetInformation function"]
ms.keywords: DFUsbRef_edde1f49-9228-48fc-8812-ebfe65f48b18.xml, WdfUsbTargetPipeGetInformation, WdfUsbTargetPipeGetInformation method, kmdf.wdfusbtargetpipegetinformation, wdf.wdfusbtargetpipegetinformation, wdfusb/WdfUsbTargetPipeGetInformation
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfUsbTargetPipeGetInformation
 - wdfusb/WdfUsbTargetPipeGetInformation
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
 - WdfUsbTargetPipeGetInformation
---

# WdfUsbTargetPipeGetInformation function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbTargetPipeGetInformation</b> method retrieves information about a USB pipe and its endpoint.

## -parameters

### -param Pipe 

[in]
A handle to a framework pipe object that was obtained by calling <a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbinterfacegetconfiguredpipe">WdfUsbInterfaceGetConfiguredPipe</a>.

### -param PipeInformation 

[out]
A pointer to a caller-allocated <a href="/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_pipe_information">WDF_USB_PIPE_INFORMATION</a> structure that receives information about the pipe and endpoint.

## -remarks

A bug check occurs if the driver supplies an invalid object handle.



For more information about the <b>WdfUsbTargetPipeGetInformation</b> method and USB I/O targets, see <a href="/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.


#### Examples

The following code example initializes a <a href="/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_pipe_information">WDF_USB_PIPE_INFORMATION</a> structure and calls <b>WdfUsbTargetPipeGetInformation</b>.

```cpp
WDF_USB_PIPE_INFORMATION pipeInfo;

WDF_USB_PIPE_INFORMATION_INIT(&pipeInfo);
WdfUsbTargetPipeGetInformation(
                               Pipe,
                               &pipeInfo
                               );
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_pipe_information">WDF_USB_PIPE_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_pipe_information_init">WDF_USB_PIPE_INFORMATION_INIT</a>



<a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbinterfacegetconfiguredpipe">WdfUsbInterfaceGetConfiguredPipe</a>