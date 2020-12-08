---
UID: NF:ks.KsEnableEvent
title: KsEnableEvent function (ks.h)
description: The KsEnableEvent function enables events requested through IOCTL_KS_ENABLE_EVENT. It responds to all event identifiers defined by the sets. This function can only be called at PASSIVE_LEVEL.
old-location: stream\ksenableevent.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsEnableEvent function"]
ms.keywords: KsEnableEvent, KsEnableEvent function [Streaming Media Devices], ks/KsEnableEvent, ksfunc_f6611298-cc8d-40eb-86e6-1287caff3ec0.xml, stream.ksenableevent
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
 - KsEnableEvent
 - ks/KsEnableEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsEnableEvent
---

# KsEnableEvent function


## -description

The <b>KsEnableEvent</b> function enables events requested through IOCTL_KS_ENABLE_EVENT. It responds to all event identifiers defined by the sets. This function can only be called at PASSIVE_LEVEL.

## -parameters

### -param Irp 

[in]
Specifies the IRP with the enable request being handled. The file object associated with the IRP is stored with the event for later comparison when disabling the event.

### -param EventSetsCount 

[in]
Indicates the number of event set structures being passed.

### -param EventSet 

[in]
Specifies a pointer to the list of event set information.

### -param EventsList 

[in, out]
If the enabling event's KSEVENT_SET.AddHandler for the event set is <b>NULL</b>, it must point to the head of the list of KSEVENT_ENTRY items on which the event is to be added. This function assumes a single list for at least a subset of events.

### -param EventsFlags 

[in, optional]
Specifies <a href="/windows-hardware/drivers/ddi/ks/ne-ks-ksevents_locktype">KSEVENTS_LOCKTYPE</a> flags specifying the type of exclusion lock to be used in accessing the event list, if any. If no flag is set, then no lock is taken. If a handler is specified already, this parameter is ignored.

### -param EventsLock 

[in, optional]
If the KSEVENT_SET.AddHandler for the event set containing the event being enabled is <b>NULL</b>, then this is used to synchronize access to the list. This value can be <b>NULL</b> if no flag is set in <i>EventsFlags</i>.

## -returns

The <b>KsEnableEvent</b> function returns STATUS_SUCCESS if successful, or an error specific to the event being enabled if unsuccessful. The function always sets the IO_STATUS_BLOCK.Information field of the PIRP.IoStatus element within the IRP to zero. It does not set the IO_STATUS_BLOCK.Status field, nor does it complete the IRP.

## -remarks

Minidrivers do not call <b>KsEnableEvent</b>. Only a pure KS driver or a class driver should call this routine.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksdisableevent">KsDisableEvent</a>
