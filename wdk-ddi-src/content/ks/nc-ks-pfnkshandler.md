---
UID: NC:ks.PFNKSHANDLER
title: PFNKSHANDLER
author: windows-driver-content
description: The minidriver-provided routine is called when Kernel Streaming receives an IOCTL_KS_METHOD, get/set property request. Provide a pointer to this handler in the relevant KSMETHOD_ITEM, KSPROPERTY_ITEM structure.
old-location: stream\kstrmethodhandler.htm
old-project: stream
ms.assetid: 717ac510-b456-43b9-9500-b07e942f424c
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KStrGetPropertyHandler, KStrHandler, KStrHandler routine [Streaming Media Devices], KStrMethodHandler, KStrSetPropertyHandler, KStrSupportHandler, PFNKSHANDLER, ks/KStrHandler, ksfunc_53b62198-4059-4715-b405-c6f55d736a09.xml, stream.kstrmethodhandler
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ks.h
api_name:
-	KStrHandler
product: Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---

# PFNKSHANDLER callback


## -description


The minidriver-provided  routine is called when Kernel Streaming receives an IOCTL_KS_METHOD, get/set property request. Provide a pointer to this handler in the relevant <a href="..\ks\ns-ks-ksmethod_item.md">KSMETHOD_ITEM</a>,  <a href="..\ks\ns-ks-ksproperty_item.md">KSPROPERTY_ITEM</a> structure.


## -prototype


````
PFNKSHANDLER KStrHandler;

NTSTATUS KStrHandler(
  _In_    PIRP          Irp,
  _In_    PKSIDENTIFIER Request,
  _Inout_ PVOID         Data
)
{ ... }
````


## -parameters




### -param Irp [in]

Specifies the IRP that contains the method or property request.


### -param Request [in]

Specifies an aligned copy of the method parameter. This is typically a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563398">KSMETHOD</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure.


### -param Data [in, out]

Specifies an aligned copy of the method data parameter or the system address of the original data parameter, depending on the flag that was specified in the <a href="..\ks\ns-ks-ksmethod_item.md">KSMETHOD_ITEM</a> structure for the method.


## -returns



Return STATUS_SUCCESS if the method is handled and the data buffer has been filled per the flag that was specified in KSMETHOD_ITEM. If returning data, your driver should set the <b>Irp-&gt;IoStatus.Information</b> field, but should not set the <b>Irp-&gt;IoStatus.Status</b> field nor should it complete the IRP. Mark the IRP pending if it is to be completed asynchronously.

Alternatively, return STATUS_SOME_NOT_MAPPED if the method has been handled but the particular request has not been completed and must be completed by the calling helper function. Return any other error message to indicate that the method is not supported or a parameter error has occurred.






## -remarks



The minidriver specifies this routine's address in the <b>MethodHandler</b> member of the <a href="..\ks\ns-ks-ksmethod_item.md">KSMETHOD_ITEM</a> structure.

The handler declaration used for <i>KStrMethodHandler</i> and <i>KStrSupportHandler</i> is also used for handlers of property and event sets, with the same parameters and return values.

When a helper function such as <a href="..\ks\nf-ks-ksmethodhandler.md">KsMethodHandler</a> calls a method handler whose data buffer is defined as a write or modify buffer, the method handler must set the <b>Information</b> member of the IO_STATUS_BLOCK structure for the <b>IoStatus</b> member within the IRP (<i>Irp</i> parameter) to the size of that data buffer. The minidriver sets the <b>Flags</b> member of the KSMETHOD_ITEM structure for the method to KSMETHOD_TYPE_WRITE or KSMETHOD_TYPE_MODIFY to define the method handler's data buffer as write or modify respectively. 

The following code snippet shows an example of an implementation of a method handler that sets the size of the returning data buffer in the IRP:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS 
  MethodHandler(PIRP pIrp, PKSIDENTIFIER Request, PVOID Data) {
    NTSTATUS Status = STATUS_UNSUCCESSFUL;
    // Pointer to hold the position on the Irp stack
    PIO_STACK_LOCATION  pIrpStack  = NULL; 
    ASSERT(pIrp);
    if(Data) {
        // Modify data here
    }
    // Find the current Irp stack.
    pIrpStack = IoGetCurrentIrpStackLocation(pIrp);
    if(pIrpStack) {
        // Set the size of the returning Irp data.
        pIrp-&gt;IoStatus.Information = 
          pIrpStack-&gt;Parameters.DeviceIoControl.OutputBufferLength;
        Status = STATUS_SUCCESS;
    }
    return(Status);
}</pre>
</td>
</tr>
</table></span></div>
The minidriver specifies this routine's address in the <b>GetPropertyHandler</b> member of the <a href="..\ks\ns-ks-ksproperty_item.md">KSPROPERTY_ITEM</a> structure.

The minidriver specifies this routine's address in the <b>SetPropertyHandler</b> member of the <a href="..\ks\ns-ks-ksproperty_item.md">KSPROPERTY_ITEM</a> structure.

The minidriver specifies this routine's address in the <b>SupportHandler</b> member of the <a href="..\ks\ns-ks-ksmethod_item.md">KSMETHOD_ITEM</a> structure.

The handler declaration used for <i>KStrMethodHandler</i> and <i>KStrSupportHandler</i> is also used for handlers of property and event sets, with the same parameters and return values.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563398">KSMETHOD</a>



<a href="..\ks\ns-ks-ksmethod_set.md">KSMETHOD_SET</a>



<a href="..\ks\ns-ks-ksmethod_item.md">KSMETHOD_ITEM</a>



<a href="..\ks\nf-ks-ksmethodhandler.md">KsMethodHandler</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNKSHANDLER routine%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

