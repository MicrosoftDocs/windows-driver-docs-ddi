---
UID: NC:usbfnattach.USBFN_GET_ATTACH_ACTION
title: USBFN_GET_ATTACH_ACTION
author: windows-driver-content
description: The filter driver's implementation that gets invoked when charger is attached to the port.
old-location: buses\usbfn_get_attach_action.htm
tech.root: usbref
ms.assetid: D951D5A0-3A93-4B67-B25A-31EE61C0A065
ms.date: 05/07/2018
ms.keywords: PFN_USBFN_GET_ATTACH_ACTION, PFN_USBFN_GET_ATTACH_ACTION callback function pointer [Buses], USBFN_GET_ATTACH_ACTION, USBFN_GET_ATTACH_ACTION callback, UsbFnGetAttachAction, UsbFnGetAttachAction callback function [Buses], buses.usbfn_get_attach_action, usbfnattach/UsbFnGetAttachAction
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	usbfnattach.h
api_name:
-	PFN_USBFN_GET_ATTACH_ACTION
product:
- Windows
targetos: Windows
req.typenames: 
---

# USBFN_GET_ATTACH_ACTION callback function


## -description


The filter driver's implementation that gets invoked when charger is attached to the port.


## -parameters




### -param Context [in]

    A pointer to a driver-defined context.


### -param OnAttach [out]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/mt188002">USBFN_ON_ATTACH</a> structure that the driver populates with the type of attach and port. 


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
 

 

