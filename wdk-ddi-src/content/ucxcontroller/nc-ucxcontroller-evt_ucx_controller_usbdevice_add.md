---
UID: NC:ucxcontroller.EVT_UCX_CONTROLLER_USBDEVICE_ADD
title: EVT_UCX_CONTROLLER_USBDEVICE_ADD
author: windows-driver-content
description: The client driver's implementation that UCX calls when a new USB device is detected.
old-location: buses\evt_ucx_controller_usbdevice_add.htm
old-project: usbref
ms.assetid: 0f89b57a-3374-4f40-88b5-43d233ba0e47
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: EVT_UCX_CONTROLLER_USBDEVICE_ADD, EvtUcxControllerUsbDeviceAdd, EvtUcxControllerUsbDeviceAdd callback function [Buses], PEVT_UCX_CONTROLLER_USBDEVICE_ADD, PEVT_UCX_CONTROLLER_USBDEVICE_ADD callback function pointer [Buses], buses.evt_ucx_controller_usbdevice_add, ucxcontroller/EvtUcxControllerUsbDeviceAdd
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ucxcontroller.h
apiname:
-	PEVT_UCX_CONTROLLER_USBDEVICE_ADD
product: Windows
targetos: Windows
req.typenames: UCM_PD_REQUEST_DATA_OBJECT, *PUCM_PD_REQUEST_DATA_OBJECT
req.product: Windows 10 or later.
---

# EVT_UCX_CONTROLLER_USBDEVICE_ADD callback


## -description


The client driver's implementation that UCX calls when a new USB device is detected.


## -prototype


````
EVT_UCX_CONTROLLER_USBDEVICE_ADD EvtUcxControllerUsbDeviceAdd;

NTSTATUS EvtUcxControllerUsbDeviceAdd(
  _In_ UCXCONTROLLER      UcxController,
  _In_ PUCXUSBDEVICE_INFO UcxUsbDeviceInfo,
  _In_ PUCXUSBDEVICE_INIT UsbDeviceInit
)
{ ... }

typedef EVT_UCX_CONTROLLER_USBDEVICE_ADD PEVT_UCX_CONTROLLER_USBDEVICE_ADD;
````


## -parameters




### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.


### -param UcxUsbDeviceInfo [in]

Pointer to a <a href="..\ucxusbdevice\ns-ucxusbdevice-_ucxusbdevice_info.md">UCXUSBDEVICE_INFO</a> structure.


### -param UsbDeviceInit [in]

Pointer to an opaque structure containing initialization
    information.  Callbacks for the device object are associated with this structure.
    This structure is managed by UCX.


## -returns



If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.




## -remarks



The UCX client driver registers its <i>EVT_UCX_CONTROLLER_USBDEVICE_ADD</i> implementation with the USB host controller extension (UCX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.

This callback function creates a new USB device object and registers the
    USB device object callback functions by calling
    <a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdevicecreate.md">UcxUsbDeviceCreate</a>.  The function may need to allocate the common buffer that will be
    used as the device context.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
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

    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&amp;objectAttributes, UCX_USB_DEVICE_CONTEXT);

    //
    // Set the event callbacks for the USB device.
    //
    UCX_USBDEVICE_EVENT_CALLBACKS_INIT(&amp;callbacks,
                                       UsbDevice_EvtUcxUsbDeviceEndpointsConfigure,
                                       UsbDevice_EvtUcxUsbDeviceEnable,
                                       UsbDevice_EvtUcxUsbDeviceDisable,
                                       UsbDevice_EvtUcxUsbDeviceReset,
                                       UsbDevice_EvtUcxUsbDeviceAddress,
                                       UsbDevice_EvtUcxUsbDeviceUpdate,
                                       UsbDevice_EvtUcxUsbDeviceHubInfo,
                                       Endpoint_EvtUcxUsbDeviceDefaultEndpointAdd,
                                       Endpoint_EvtUcxUsbDeviceEndpointAdd);

    UcxUsbDeviceInitSetEventCallbacks(UsbDeviceInit, &amp;callbacks);

    //
    // Create the device
    //
    status = UcxUsbDeviceCreate(UcxController,
                                &amp;UsbDeviceInit,
                                &amp;objectAttributes,
                                &amp;ucxUsbDevice);

    if (!NT_SUCCESS(status)) {
        DbgTrace(TL_ERROR, UsbDevice, "UcxUsbDeviceCreate Failed %!STATUS!", status);
        goto EvtControllerUsbDeviceAddEnd;
    }

    ucxUsbDeviceContext = GetUcxUsbDeviceContext(ucxUsbDevice);
    ucxUsbDeviceContext-&gt;DeviceSpeed = UsbDeviceInfo-&gt;DeviceSpeed;
    ucxUsbDeviceContext-&gt;TtHub = UsbDeviceInfo-&gt;TtHub;
    RtlCopyMemory(&amp;ucxUsbDeviceContext-&gt;PortPath,
                  &amp;UsbDeviceInfo-&gt;PortPath,
                  sizeof(USB_DEVICE_PORT_PATH));

    DbgTrace(TL_INFO, UsbDevice, "UsbDevice_EvtControllerUsbDeviceAdd");

EvtControllerUsbDeviceAddEnd:

    return status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UCX_CONTROLLER_USBDEVICE_ADD callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

