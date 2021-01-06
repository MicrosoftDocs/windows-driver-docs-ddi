---
UID: NF:usbdlib.USBD_UrbAllocate
title: USBD_UrbAllocate function (usbdlib.h)
description: The USBD_UrbAllocate routine allocates a USB Request Block (URB).
old-location: buses\usbd_urballocate.htm
tech.root: usbref
ms.date: 06/24/2019
keywords: ["USBD_UrbAllocate function"]
ms.keywords: USBD_UrbAllocate, USBD_UrbAllocate routine [Buses], buses.usbd_urballocate, usbdlib/USBD_UrbAllocate
req.header: usbdlib.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Requires WDK for Windows 8. Targets Windows Vista and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Usbdex.lib
req.dll: 
req.irql: DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - USBD_UrbAllocate
 - usbdlib/USBD_UrbAllocate
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Usbdex.lib
 - Usbdex.dll
api_name:
 - USBD_UrbAllocate
---

# USBD_UrbAllocate function


## -description

The <b>USBD_UrbAllocate</b> routine allocates a USB Request Block (URB).

## -parameters

### -param USBDHandle 

[in]
USBD handle that is retrieved by the client driver in a previous call to  the <a href="/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_createhandle">USBD_CreateHandle</a> routine.

### -param Urb 

[out]
Pointer to the newly allocated <a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a> structure. All members of the structure are set to zero. The client driver must free the URB when the driver has finished using it by calling <a href="/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_urbfree">USBD_UrbFree</a>.

## -returns

The <b>USBD_UrbAllocate</b> routine returns STATUS_SUCCESS if the request is successful. Otherwise,  <b>USBD_UrbAllocate</b> sets <i>Urb</i> to NULL and returns a failure code. 

Possible values include, but are not limited to, STATUS_INVALID_PARAMETER, which  indicates the caller passed in NULL to <i>USBDHandle</i> or <i>Urb</i>.

## -remarks

The <b>USBD_UrbAllocate</b> routine enables the underlying USB driver stack to allocate an opaque URB context for the URB. By using the URB context, the USB driver stack can process requests more efficiently and reliably. Those optimizations are provided by the USB 3.0 driver stack that is included in Windows 8. The client driver cannot access the URB context; the context is used internally by the bus driver. 

Regardless of the USB protocol version of the host controller, the underlying USB driver stack, the target operating system, the client driver must always call <b>USBD_UrbAllocate</b> to allocate an <a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a> structure.  <b>USBD_UrbAllocate</b> replaces earlier allocation mechanisms, such as  <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a>, or allocating them on the stack. 

The client driver must <i>not</i> use <b>USBD_UrbAllocate</b>, 

<ul>
<li>To allocate an URB that has variable length, such as an URB for an isochronous transfer. Instead the client driver must call <a href="/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_isochurballocate">USBD_IsochUrbAllocate</a>. </li>
<li>If the target operating system is Windows XP with Service Pack 2 (SP2) or an earlier version of Windows.</li>
</ul>
For more information about replacement routines, see <a href="/windows-hardware/drivers/usbcon/how-to-add-xrb-support-for-client-drivers">Allocating and Building URBs</a>.

You must call <a href="/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_urbfree">USBD_UrbFree</a> to release the URB allocated by <b>USBD_UrbAllocate</b>. 


#### Examples

The following code example shows how to allocate, submit, and release a URB. The example submits the URB synchronously. For the implementation of the SubmitUrbSync function, see the example section in [How to Submit an URB](/windows-hardware/drivers/usbcon/send-requests-to-the-usb-driver-stack).


```cpp
NTSTATUS CreateandSubmitURBSynchronously (
    _In_ USBD_HANDLE USBDHandle 
{
    PURB    Urb = NULL;

    NTSTATUS status;

    status = USBD_UrbAllocate(USBDHandle, &Urb);

    if (!NT_SUCCESS(status))
    {
        goto CreateandSubmitURBExit;
    }

    //Format the URB for the request. Not Shown.
    status = BuildURBForBulkTransfer (Urb);

    if (!NT_SUCCESS(status))
    {
        goto CreateandSubmitURBExit;
    }

    status = SubmitUrbSync( TargetDeviceObject,
        Urb)  

    if (!NT_SUCCESS(status))
    {
        goto CreateandSubmitURBExit;
    }

CreateandSubmitURBExit:

    if (Urb)
    {
        USBD_UrbFree( USBDHandle, Urb); 
    }

    return status;

}

```


## -see-also

<a href="/windows-hardware/drivers/usbcon/how-to-add-xrb-support-for-client-drivers">Allocating and Building URBs</a>



<a href="/windows-hardware/drivers/ddi/index">Sending Requests to a USB Device</a>



<a href="/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_urbfree">USBD_UrbFree</a>
