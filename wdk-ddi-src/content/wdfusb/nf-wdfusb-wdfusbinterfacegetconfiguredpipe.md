---
UID: NF:wdfusb.WdfUsbInterfaceGetConfiguredPipe
title: WdfUsbInterfaceGetConfiguredPipe function (wdfusb.h)
description: The WdfUsbInterfaceGetConfiguredPipe method returns a handle to the framework pipe object that is associated with a specified USB device interface and pipe index. Optionally, the method also returns information about the pipe.
old-location: wdf\wdfusbinterfacegetconfiguredpipe.htm
tech.root: wdf
ms.assetid: 0836a969-e484-485f-9b65-202c177b4f43
ms.date: 02/26/2018
keywords: ["WdfUsbInterfaceGetConfiguredPipe function"]
ms.keywords: DFUsbRef_65a97d99-39c5-4750-95e1-6c9c20c169bb.xml, WdfUsbInterfaceGetConfiguredPipe, WdfUsbInterfaceGetConfiguredPipe method, kmdf.wdfusbinterfacegetconfiguredpipe, wdf.wdfusbinterfacegetconfiguredpipe, wdfusb/WdfUsbInterfaceGetConfiguredPipe
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
 - WdfUsbInterfaceGetConfiguredPipe
 - wdfusb/WdfUsbInterfaceGetConfiguredPipe
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
 - WdfUsbInterfaceGetConfiguredPipe
---

# WdfUsbInterfaceGetConfiguredPipe function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbInterfaceGetConfiguredPipe</b> method returns a handle to the framework pipe object that is associated with a specified USB device interface and pipe index. Optionally, the method also returns information about the pipe.

## -parameters

### -param UsbInterface 

[in]
A handle to a USB interface object that was obtained by calling <a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicegetinterface">WdfUsbTargetDeviceGetInterface</a>.

### -param PipeIndex 

[in]
A zero-based index into the set of framework pipe objects that are associated with the specified interface object.

### -param PipeInfo 

[out, optional]
A pointer to a caller-allocated <a href="/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_pipe_information">WDF_USB_PIPE_INFORMATION</a> structure that the framework fills in. This parameter is optional and can be <b>NULL</b>.

## -returns

If the operation succeeds, <b>WdfUsbInterfaceGetConfiguredPipe</b> returns a handle to the framework pipe object that is associated with the specified interface object and pipe index. The method returns <b>NULL</b> if the <a href="/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_pipe_information">WDF_USB_PIPE_INFORMATION</a> structure's size is incorrect or if the pipe index value is too large.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

Your driver can call <b>WdfUsbInterfaceGetConfiguredPipe</b> after it has called <a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdeviceselectconfig">WdfUsbTargetDeviceSelectConfig</a>.

For more information about the <b>WdfUsbInterfaceGetConfiguredPipe</b> method and USB I/O targets, see <a href="/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.


#### Examples

The following code example sends a USB abort request to each configured pipe of a specified USB interface.

```cpp
BYTE  count, i;
NTSTATUS  status;

count = WdfUsbInterfaceGetNumConfiguredPipes(UsbInterface);

for (i = 0; i < count; i++) {
    WDFUSBPIPE pipe;
    pipe = WdfUsbInterfaceGetConfiguredPipe(
                                            UsbInterface,
                                            i,
                                            NULL
                                            );
    status = WdfUsbTargetPipeAbortSynchronously(
                                            pipe,
                                            WDF_NO_HANDLE,
                                            NULL
                                            );

    if (!NT_SUCCESS(status)) {
        break;
    }
}
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_pipe_information">WDF_USB_PIPE_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbinterfacegetnumconfiguredpipes">WdfUsbInterfaceGetNumConfiguredPipes</a>



<a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicegetinterface">WdfUsbTargetDeviceGetInterface</a>



<a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdeviceselectconfig">WdfUsbTargetDeviceSelectConfig</a>