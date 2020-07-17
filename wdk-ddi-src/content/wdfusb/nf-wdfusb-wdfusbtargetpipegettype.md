---
UID: NF:wdfusb.WdfUsbTargetPipeGetType
title: WdfUsbTargetPipeGetType function (wdfusb.h)
description: The WdfUsbTargetPipeGetType method returns the type of a specified USB pipe.
old-location: wdf\wdfusbtargetpipegettype.htm
tech.root: wdf
ms.assetid: d02af0c8-f963-4bec-a8b6-fe334fd75a68
ms.date: 02/26/2018
keywords: ["WdfUsbTargetPipeGetType function"]
ms.keywords: DFUsbRef_de8bc76f-0be3-46bb-a959-b3115e91b472.xml, WdfUsbTargetPipeGetType, WdfUsbTargetPipeGetType method, kmdf.wdfusbtargetpipegettype, wdf.wdfusbtargetpipegettype, wdfusb/WdfUsbTargetPipeGetType
f1_keywords:
 - "wdfusb/WdfUsbTargetPipeGetType"
 - "WdfUsbTargetPipeGetType"
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
- WdfUsbTargetPipeGetType
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetPipeGetType function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbTargetPipeGetType</b> method returns the type of a specified USB pipe.


## -parameters




### -param Pipe [in]

A handle to a framework pipe object that was obtained by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbinterfacegetconfiguredpipe">WdfUsbInterfaceGetConfiguredPipe</a>. 


## -returns



<b>WdfUsbTargetPipeGetType</b> returns a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ne-wdfusb-_wdf_usb_pipe_type">WDF_USB_PIPE_TYPE</a>-typed value that identifies the specified pipe's type. 

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



For more information about the <b>WdfUsbTargetPipeGetType</b> method and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.


#### Examples

The following code example determines the type of a USB pipe.

```cpp
WDF_USB_PIPE_TYPEusbPipeType;

usbPipeType = WdfUsbTargetPipeGetType(usbPipe);
 
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ne-wdfusb-_wdf_usb_pipe_type">WDF_USB_PIPE_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbinterfacegetconfiguredpipe">WdfUsbInterfaceGetConfiguredPipe</a>
 

 

