---
UID: NF:ks.KsDefaultAddEventHandler
title: KsDefaultAddEventHandler function (ks.h)
description: The KsDefaultAddEventHandler function is a default routine to handle event 'add' requests.
old-location: stream\ksdefaultaddeventhandler.htm
tech.root: stream
ms.assetid: 8e429a48-4e86-4673-aa32-85b640e2f64f
ms.date: 04/23/2018
keywords: ["KsDefaultAddEventHandler function"]
ms.keywords: KsDefaultAddEventHandler, KsDefaultAddEventHandler function [Streaming Media Devices], avfunc_7e4e393b-c3ab-4538-8790-9fe4c4f964cd.xml, ks/KsDefaultAddEventHandler, stream.ksdefaultaddeventhandler
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KsDefaultAddEventHandler
 - ks/KsDefaultAddEventHandler
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsDefaultAddEventHandler
---

# KsDefaultAddEventHandler function


## -description

The<b> KsDefaultAddEventHandler </b>function is a default routine to handle event 'add' requests.

## -parameters

### -param Irp 

[in]
The event <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>. This contains the object into which the event is inserted.

### -param EventData 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-kseventdata">KSEVENTDATA</a> structure that describes an event notification method.

### -param EventEntry 

[in, out]
The event entry that is to be inserted into the object's event list. The object is determined by <i>Irp</i>.

## -returns

Returns the success or failure of adding the event into the object's event list.

## -remarks

<b>KsDefaultAddEventHandler</b> determines the relevant object from <i>Irp</i> and adds the specified event to the object's event list.

This is functionally equivalent to <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksaddevent">KsAddEvent</a> (or <b>Ks</b><i>Xxx</i><b>AddEvent</b>, see below) for the object that is associated with <i>Irp</i>. Use <b>KsDefaultAddEventHandler</b> from a minidriver-specified <i>AddEvent</i> handler to insert the event into the object's event list.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksevent_entry">KSEVENT_ENTRY</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksaddevent">KsAddEvent</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksfilteraddevent">KsFilterAddEvent</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgenerateevents">KsGenerateEvents</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspinaddevent">KsPinAddEvent</a>