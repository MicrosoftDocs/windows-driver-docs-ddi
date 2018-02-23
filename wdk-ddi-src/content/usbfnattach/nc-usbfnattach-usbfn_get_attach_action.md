---
UID: NC:usbfnattach.USBFN_GET_ATTACH_ACTION
title: USBFN_GET_ATTACH_ACTION
author: windows-driver-content
description: The filter driver's implementation that gets invoked when charger is attached to the port.
old-location: buses\usbfn_get_attach_action.htm
old-project: UsbRef
ms.assetid: D951D5A0-3A93-4B67-B25A-31EE61C0A065
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: buses.usbfn_get_attach_action, UsbFnGetAttachAction callback function [Buses], UsbFnGetAttachAction, USBFN_GET_ATTACH_ACTION, USBFN_GET_ATTACH_ACTION, usbfnattach/UsbFnGetAttachAction, PFN_USBFN_GET_ATTACH_ACTION callback function pointer [Buses], PFN_USBFN_GET_ATTACH_ACTION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: usbfnattach.h
req.include-header: 
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
-	usbfnattach.h
apiname:
-	PFN_USBFN_GET_ATTACH_ACTION
product: Windows
targetos: Windows
req.typenames: USBD_INTERFACE_LIST_ENTRY, *PUSBD_INTERFACE_LIST_ENTRY
req.product: Windows 10 or later.
---

# USBFN_GET_ATTACH_ACTION callback


## -description


The filter driver's implementation that gets invoked when charger is attached to the port.


## -prototype


````
USBFN_GET_ATTACH_ACTION UsbFnGetAttachAction;

NTSTATUS UsbFnGetAttachAction(
  _In_  PVOID            Context,
  _Out_ PUSBFN_ON_ATTACH OnAttach
)
{ ... }

typedef USBFN_GET_ATTACH_ACTION PFN_USBFN_GET_ATTACH_ACTION;
````


## -parameters




### -param Context [in]

    A pointer to a driver-defined context.


### -param OnAttach [out]

A pointer to a caller-allocated <a href="..\usbfnattach\ns-usbfnattach-_usbfn_on_attach.md">USBFN_ON_ATTACH</a> structure that the driver populates with the type of attach and port. 


## -returns



If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.




## -remarks



To support attach and detatch detection, the USB lower filter driver must publish its support. During the publishing process, the driver also registers its implementation of this  callback function. For more information, see <a href="https://msdn.microsoft.com/05D2B46A-282C-4B75-9F5C-2FC0AF344AB9">USB filter driver for supporting proprietary chargers</a>.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
UsbLowerFilter_GetAttachAction(
    __in PVOID Context,
    __out PUSBFN_ON_ATTACH OnAttach
    )
{
    NTSTATUS Status;
    PPDCP_CONTEXT PdcpContext = NULL;
    LARGE_INTEGER Timeout;
    
    PAGED_CODE();

    // Get driver context
    PdcpContext = DeviceGetUsbLowerFilterContext((WDFDEVICE)Context);

    // Clear the event
    KeClearEvent(&amp;PdcpContext-&gt;AbortAttachOperation);

    // Wait for a while
    Timeout.QuadPart = WDF_REL_TIMEOUT_IN_MS(PdcpContext-&gt;DetectionDelayInms);

    Status = KeWaitForSingleObject(
        &amp;PdcpContext-&gt;AbortAttachOperation,
        Executive,
        KernelMode,
        FALSE,
        &amp;Timeout);

    switch (Status)
    {
    case STATUS_SUCCESS:
        // The abort event was set.
        Status = STATUS_REQUEST_ABORTED;
        break;

    case STATUS_TIMEOUT:
        Status = STATUS_SUCCESS;
        break;

    default:
        break;
    }

    if (NT_SUCCESS(Status))
    {
        OnAttach-&gt;AttachAction = PdcpContext-&gt;CurrentAttachAction;
        OnAttach-&gt;PortType = PdcpContext-&gt;CurrentPortType;
    }

    return Status;
</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="https://msdn.microsoft.com/05D2B46A-282C-4B75-9F5C-2FC0AF344AB9">USB filter driver for supporting proprietary chargers</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20USBFN_GET_ATTACH_ACTION callback function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

