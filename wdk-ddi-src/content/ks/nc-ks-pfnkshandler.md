---
UID: NC:ks.PFNKSHANDLER
title: PFNKSHANDLER (ks.h)
description: The minidriver-provided routine is called when Kernel Streaming receives an IOCTL_KS_METHOD, get/set property request. Provide a pointer to this handler in the relevant KSMETHOD_ITEM, KSPROPERTY_ITEM structure.
old-location: stream\kstrmethodhandler.htm
tech.root: stream
ms.assetid: 717ac510-b456-43b9-9500-b07e942f424c
ms.date: 04/23/2018
keywords: ["PFNKSHANDLER callback function"]
ms.keywords: KStrGetPropertyHandler, KStrHandler, KStrHandler routine [Streaming Media Devices], KStrMethodHandler, KStrSetPropertyHandler, KStrSupportHandler, PFNKSHANDLER, ks/KStrHandler, ksfunc_53b62198-4059-4715-b405-c6f55d736a09.xml, stream.kstrmethodhandler
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PFNKSHANDLER
 - ks/PFNKSHANDLER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ks.h
api_name:
 - KStrHandler
---

# PFNKSHANDLER callback function


## -description

The minidriver-provided  routine is called when Kernel Streaming receives an IOCTL_KS_METHOD, get/set property request. Provide a pointer to this handler in the relevant [KSMETHOD_ITEM](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksmethod_item), [KSPROPERTY_ITEM](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_item) structure.

## -parameters

### -param Irp 

[in]
Specifies the IRP that contains the method or property request.

### -param Request 

[in]
Specifies an aligned copy of the method parameter. This is typically a pointer to a [KSMETHOD](https://docs.microsoft.com/previous-versions/ff563398(v=vs.85)) or [KSPROPERTY](https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)) structure.

### -param Data 

[in, out]
Specifies an aligned copy of the method data parameter or the system address of the original data parameter, depending on the flag that was specified in the [KSMETHOD_ITEM](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksmethod_item) structure for the method.

## -returns

Return STATUS_SUCCESS if the method is handled and the data buffer has been filled per the flag that was specified in KSMETHOD_ITEM. If returning data, your driver should set the **Irp->IoStatus.Information** field, but should not set the **Irp->IoStatus.Status** field nor should it complete the IRP. Mark the IRP pending if it is to be completed asynchronously.

Alternatively, return STATUS_SOME_NOT_MAPPED if the method has been handled but the particular request has not been completed and must be completed by the calling helper function. Return any other error message to indicate that the method is not supported or a parameter error has occurred.

## -remarks

The minidriver specifies this routine's address in the **MethodHandler** member of the [KSMETHOD_ITEM](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksmethod_item) structure.

The handler declaration used for *KStrMethodHandler* and *KStrSupportHandler* is also used for handlers of property and event sets, with the same parameters and return values.

When a helper function such as [KsMethodHandler](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksmethodhandler) calls a method handler whose data buffer is defined as a write or modify buffer, the method handler must set the **Information** member of the IO_STATUS_BLOCK structure for the **IoStatus** member within the IRP (*Irp* parameter) to the size of that data buffer. The minidriver sets the **Flags** member of the KSMETHOD_ITEM structure for the method to KSMETHOD_TYPE_WRITE or KSMETHOD_TYPE_MODIFY to define the method handler's data buffer as write or modify respectively.

The following code snippet shows an example of an implementation of a method handler that sets the size of the returning data buffer in the IRP:

```cpp
NTSTATUS
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
        pIrp->IoStatus.Information =
          pIrpStack->Parameters.DeviceIoControl.OutputBufferLength;
        Status = STATUS_SUCCESS;
    }
    return(Status);
}
```

The minidriver specifies this routine's address in the **GetPropertyHandler** member of the [KSPROPERTY_ITEM](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_item) structure.

The minidriver specifies this routine's address in the **SetPropertyHandler** member of the [KSPROPERTY_ITEM](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_item) structure.

The minidriver specifies this routine's address in the **SupportHandler** member of the [KSMETHOD_ITEM](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksmethod_item) structure.

The handler declaration used for *KStrMethodHandler* and *KStrSupportHandler* is also used for handlers of property and event sets, with the same parameters and return values.

## -see-also

[KSMETHOD](https://docs.microsoft.com/previous-versions/ff563398(v=vs.85))

[KSMETHOD_ITEM](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksmethod_item)

[KSMETHOD_SET](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksmethod_set)

[KsMethodHandler](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksmethodhandler)

