---
UID: NF:ks.KsEnableEventWithAllocator
title: KsEnableEventWithAllocator function (ks.h)
description: The KsEnableEventWithAllocator function enables events requested through IOCTL_KS_ENABLE_EVENT but also allows an optional allocator callback to be used to provide a buffer for the parameters.
tech.root: stream
ms.date: 07/13/2022
keywords: ["KsEnableEventWithAllocator function"]
ms.keywords: KsEnableEventWithAllocator, KsEnableEventWithAllocator function [Streaming Media Devices], ks/KsEnableEventWithAllocator, ksfunc_2af8f81f-ef1d-4ad5-9267-dfdc14005183.xml, stream.ksenableeventwithallocator
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - KsEnableEventWithAllocator
 - ks/KsEnableEventWithAllocator
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsEnableEventWithAllocator
---

## -description

The **KsEnableEventWithAllocator** function enables events requested through IOCTL_KS_ENABLE_EVENT but also allows an optional allocator callback to be used to provide a buffer for the parameters. It responds to all event identifiers defined by the sets. This function can only be called at PASSIVE_LEVEL.

If used, the filter may need to free the buffer in some nonconventional manner. Note that the IRP_BUFFERED_IO and IRP_DEALLOCATE_BUFFER flags are not set when using a custom allocator.

## -parameters

### -param Irp [in]

Specifies the IRP with the enable request being handled. The file object associated with the IRP is stored with the event for later comparison when disabling the event.

### -param EventSetsCount [in]

Indicates the number of event set structures being passed.

### -param EventSet [in]

Specifies a pointer to the list of event set information.

### -param EventsList [in, out]

If the enabling event's KSEVENT_SET.AddHandler for the event set is **NULL**, it must point to the head of the list of KSEVENT_ENTRY items on which the event is to be added. This function assumes a single list for at least a subset of events.

### -param EventsFlags [in, optional]

Specifies [KSEVENTS_LOCKTYPE](./ne-ks-ksevents_locktype.md) flags specifying the type of exclusion lock to be used in accessing the event list, if any. If no flag is set, then no lock is taken. If a handler is specified already, this parameter is ignored.

### -param EventsLock [in, optional]

If the KSEVENT_SET.AddHandler for the event set containing the event being enabled is **NULL**, then this is used to synchronize access to the list. This value can be **NULL** if no flag is set in *EventsFlags*.

### -param Allocator [in, optional]

Optionally points to an allocation function that will be used to allocate memory to store the event parameters.

### -param EventItemSize [in, optional]

Optionally contains the size of each KSEVENT_ITEM structure in each list of events. The event item may be extended in order to store private information. If this parameter is zero, the structure size is assumed to be normal. If it is greater than or equal to an event item structure, the KSEVENT_ITEM_IRP_STORAGE macro can be used to return a pointer to the event item so the custom data can be retrieved. On 64-bit platforms, this parameter must be a multiple of 8.

## -returns

Same as **KsEnableEvent**, which returns STATUS_SUCCESS if successful, or an error specific to the event being enabled if unsuccessful. The function always sets the IO_STATUS_BLOCK.Information field of the PIRP.IoStatus element within the IRP to zero. It does not set the IO_STATUS_BLOCK.Status field, nor does it complete the IRP.

## -remarks

If the optional allocator callback is used, the filter may need to free the buffer in some nonconventional manner. Note that the IRP_BUFFERED_IO and IRP_DEALLOCATE_BUFFER flags are not set when using a custom allocator.