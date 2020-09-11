---
UID: NC:ucxcontroller.EVT_UCX_CONTROLLER_USBDEVICE_ADD
title: EVT_UCX_CONTROLLER_USBDEVICE_ADD (ucxcontroller.h)
description: The client driver's implementation that UCX calls when a new USB device is detected.
old-location: buses\evt_ucx_controller_usbdevice_add.htm
tech.root: usbref
ms.assetid: 0f89b57a-3374-4f40-88b5-43d233ba0e47
ms.date: 05/07/2018
keywords: ["EVT_UCX_CONTROLLER_USBDEVICE_ADD callback function"]
ms.keywords: EVT_UCX_CONTROLLER_USBDEVICE_ADD, EVT_UCX_CONTROLLER_USBDEVICE_ADD callback, EvtUcxControllerUsbDeviceAdd, EvtUcxControllerUsbDeviceAdd callback function [Buses], PEVT_UCX_CONTROLLER_USBDEVICE_ADD, PEVT_UCX_CONTROLLER_USBDEVICE_ADD callback function pointer [Buses], buses.evt_ucx_controller_usbdevice_add, ucxcontroller/EvtUcxControllerUsbDeviceAdd
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_UCX_CONTROLLER_USBDEVICE_ADD
 - ucxcontroller/EVT_UCX_CONTROLLER_USBDEVICE_ADD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ucxcontroller.h
api_name:
 - PEVT_UCX_CONTROLLER_USBDEVICE_ADD
---

# EVT_UCX_CONTROLLER_USBDEVICE_ADD callback function


## -description

The client driver's implementation that UCX calls when a new USB device is detected.

## -parameters

### -param UcxController 

[in]
 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a> method.

### -param UcxUsbDeviceInfo 

[in]
Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_ucxusbdevice_info">UCXUSBDEVICE_INFO</a> structure.

### -param UsbDeviceInit 

[in]
Pointer to an opaque structure containing initialization
    information.  Callbacks for the device object are associated with this structure.
    This structure is managed by UCX.

## -returns

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.

## -remarks

The UCX client driver registers its <i>EVT_UCX_CONTROLLER_USBDEVICE_ADD</i> implementation with the USB host controller extension (UCX) by calling the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a> method.

This callback function creates a new USB device object and registers the
    USB device object callback functions by calling
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/nf-ucxusbdevice-ucxusbdevicecreate">UcxUsbDeviceCreate</a>.  The function may need to allocate the common buffer that will be
    used as the device context.


#### Examples


```
NTSTATUS
UsbDevice_EvtControllerUsbDeviceAdd(
    UCXCONTROLLER       UcxController,
    PUCXUSBDEVICE_INFO  UsbDeviceInfo,
    PUCXUSBDEVICE_INIT  UsbDeviceInit
)

{
    NTSTATUS                        status = STATUS_SUCCESS;

    WDF_OBJECT_ATTRIBUTES           objectAttributes;
    UCX_USBDEVICE_EVENT_CALLBACKS   callbacks;

    UCXUSBDEVICE                    ucxUsbDevice;
    PUCX_USB_DEVICE_CONTEXT         ucxUsbDeviceContext;

    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&objectAttributes, UCX_USB_DEVICE_CONTEXT);

    //
    // Set the event callbacks for the USB device.
    //
    UCX_USBDEVICE_EVENT_CALLBACKS_INIT(&callbacks,
                                       UsbDevice_EvtUcxUsbDeviceEndpointsConfigure,
                                       UsbDevice_EvtUcxUsbDeviceEnable,
                                       UsbDevice_EvtUcxUsbDeviceDisable,
                                       UsbDevice_EvtUcxUsbDeviceReset,
                                       UsbDevice_EvtUcxUsbDeviceAddress,
                                       UsbDevice_EvtUcxUsbDeviceUpdate,
                                       UsbDevice_EvtUcxUsbDeviceHubInfo,
                                       Endpoint_EvtUcxUsbDeviceDefaultEndpointAdd,
                                       Endpoint_EvtUcxUsbDeviceEndpointAdd);

    UcxUsbDeviceInitSetEventCallbacks(UsbDeviceInit, &callbacks);

    //
    // Create the device
    //
    status = UcxUsbDeviceCreate(UcxController,
                                &UsbDeviceInit,
                                &objectAttributes,
                                &ucxUsbDevice);

    if (!NT_SUCCESS(status)) {
        DbgTrace(TL_ERROR, UsbDevice, "UcxUsbDeviceCreate Failed %!STATUS!", status);
        goto EvtControllerUsbDeviceAddEnd;
    }

    ucxUsbDeviceContext = GetUcxUsbDeviceContext(ucxUsbDevice);
    ucxUsbDeviceContext->DeviceSpeed = UsbDeviceInfo->DeviceSpeed;
    ucxUsbDeviceContext->TtHub = UsbDeviceInfo->TtHub;
    RtlCopyMemory(&ucxUsbDeviceContext->PortPath,
                  &UsbDeviceInfo->PortPath,
                  sizeof(USB_DEVICE_PORT_PATH));

    DbgTrace(TL_INFO, UsbDevice, "UsbDevice_EvtControllerUsbDeviceAdd");

EvtControllerUsbDeviceAddEnd:

    return status;
}
```


## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188033(v=vs.85)">UcxControllerCreate</a>

