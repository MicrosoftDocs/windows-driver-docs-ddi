---
UID: NF:usbdlib.USBD_UrbAllocate
title: USBD_UrbAllocate function (usbdlib.h)
description: The USBD_UrbAllocate routine allocates a USB Request Block (URB).
old-location: buses\usbd_urballocate.htm
tech.root: usbref
ms.assetid: 384E04BE-794F-4F87-81E5-35B974EB6172
ms.date: 05/07/2018
ms.keywords: USBD_UrbAllocate, USBD_UrbAllocate routine [Buses], buses.usbd_urballocate, usbdlib/USBD_UrbAllocate
ms.topic: function
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# USBD_UrbAllocate function


## -description


The <b>USBD_UrbAllocate</b> routine allocates a USB Request Block (URB).


## -parameters




### -param USBDHandle [in]

USBD handle that is retrieved by the client driver in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406241">USBD_CreateHandle</a> routine.


### -param Urb [out]

Pointer to the newly allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a> structure. All members of the structure are set to zero. The client driver must free the URB when the driver has finished using it by calling <a href="https://msdn.microsoft.com/library/windows/hardware/hh406252">USBD_UrbFree</a>.


## -returns



The <b>USBD_UrbAllocate</b> routine returns STATUS_SUCCESS if the request is successful. Otherwise,  <b>USBD_UrbAllocate</b> sets <i>Urb</i> to NULL and returns a failure code. 

Possible values include, but are not limited to, STATUS_INVALID_PARAMETER, which  indicates the caller passed in NULL to <i>USBDHandle</i> or <i>Urb</i>.




## -remarks



The <b>USBD_UrbAllocate</b> routine enables the underlying USB driver stack to allocate an opaque URB context for the URB. By using the URB context, the USB driver stack can process requests more efficiently and reliably. Those optimizations are provided by the USB 3.0 driver stack that is included in Windows 8. The client driver cannot access the URB context; the context is used internally by the bus driver. 

Regardless of the USB protocol version of the host controller, the underlying USB driver stack, the target operating system, the client driver must always call <b>USBD_UrbAllocate</b> to allocate an <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a> structure.  <b>USBD_UrbAllocate</b> replaces earlier allocation mechanisms, such as  <a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a>, or allocating them on the stack. 

The client driver must <i>not</i> use <b>USBD_UrbAllocate</b>, 

<ul>
<li>To allocate an URB that has variable length, such as an URB for an isochronous transfer. Instead the client driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/hh406231">USBD_IsochUrbAllocate</a>. </li>
<li>If the target operating system is Windows XP with Service Pack 2 (SP2) or an earlier version of Windows.</li>
</ul>
For more information about replacement routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh450844">Allocating and Building URBs</a>.

You must call <a href="https://msdn.microsoft.com/library/windows/hardware/hh406252">USBD_UrbFree</a> to release the URB allocated by <b>USBD_UrbAllocate</b>. 


#### Examples

The following code example shows how to allocate, submit, and release a URB. The example submits the URB synchronously. For the implementation of the SubmitUrbSync function, see the example section in [How to Submit an URB](https://docs.microsoft.com/windows-hardware/drivers/usbcon/send-requests-to-the-usb-driver-stack).

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>NTSTATUS CreateandSubmitURBSynchronously (
    _In_ USBD_HANDLE USBDHandle 
{
    PURB    Urb = NULL;

    NTSTATUS status;

    status = USBD_UrbAllocate(USBDHandle, &amp;Urb);

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
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450844">Allocating and Building URBs</a>



<a href="https://msdn.microsoft.com/15be1e51-5ab2-40c4-95a8-8555c92523aa">Sending Requests to a USB Device</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406252">USBD_UrbFree</a>
 

 

