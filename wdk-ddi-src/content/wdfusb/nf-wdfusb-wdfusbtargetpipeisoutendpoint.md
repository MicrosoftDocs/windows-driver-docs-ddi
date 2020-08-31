---
UID: NF:wdfusb.WdfUsbTargetPipeIsOutEndpoint
title: WdfUsbTargetPipeIsOutEndpoint function (wdfusb.h)
description: The WdfUsbTargetPipeIsOutEndpoint method determines whether a specified USB pipe is connected to an output endpoint.
old-location: wdf\wdfusbtargetpipeisoutendpoint.htm
tech.root: wdf
ms.assetid: 803d282b-f6eb-4cd3-91b3-899f983c9dc5
ms.date: 02/26/2018
keywords: ["WdfUsbTargetPipeIsOutEndpoint function"]
ms.keywords: DFUsbRef_19c3e865-4f6c-4950-93af-46a8b97ec6b9.xml, WdfUsbTargetPipeIsOutEndpoint, WdfUsbTargetPipeIsOutEndpoint method, kmdf.wdfusbtargetpipeisoutendpoint, wdf.wdfusbtargetpipeisoutendpoint, wdfusb/WdfUsbTargetPipeIsOutEndpoint
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
 - WdfUsbTargetPipeIsOutEndpoint
 - wdfusb/WdfUsbTargetPipeIsOutEndpoint
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
 - WdfUsbTargetPipeIsOutEndpoint
---

# WdfUsbTargetPipeIsOutEndpoint function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbTargetPipeIsOutEndpoint</b> method determines whether a specified USB pipe is connected to an output endpoint.

## -parameters

### -param Pipe 

[in]
A handle to a framework pipe object that represents a bulk pipe or interrupt pipe and was obtained by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbinterfacegetconfiguredpipe">WdfUsbInterfaceGetConfiguredPipe</a>.

## -returns

<b>WdfUsbTargetPipeIsOutEndpoint</b> returns <b>TRUE</b> if the pipe that the <i>Pipe</i> handle represents an output endpoint. The method returns <b>FALSE</b> if the endpoint is an input endpoint.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

For more information about the <b>WdfUsbTargetPipeIsOutEndpoint</b> method and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.


#### Examples

The following code example determines whether a specified USB pipe is connected to an output endpoint.

```cpp
BOOLEAN isOutEndPoint;

isOutEndPoint = WdfUsbTargetPipeIsOutEndpoint(usbPipe);
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_pipe_direction_out">WDF_USB_PIPE_DIRECTION_OUT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbinterfacegetconfiguredpipe">WdfUsbInterfaceGetConfiguredPipe</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetpipeisinendpoint">WdfUsbTargetPipeIsInEndpoint</a>

