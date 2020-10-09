---
UID: NC:ks.PFNKSREMOVEEVENT
title: PFNKSREMOVEEVENT (ks.h)
description: An AVStream minidriver's AVStrMiniRemoveEvent routine is called when a client requests to be removed from the notification queue for an event. This routine is optional.
old-location: stream\avstrminiremoveevent.htm
tech.root: stream
ms.assetid: dee4ce19-9dc8-4728-855b-eadb5bca0fc2
ms.date: 04/23/2018
keywords: ["PFNKSREMOVEEVENT callback function"]
ms.keywords: AVStrMiniRemoveEvent, AVStrMiniRemoveEvent routine [Streaming Media Devices], PFNKSREMOVEEVENT, avstclbk_04bc810f-666a-4b24-9bc9-e203ebbbbf29.xml, ks/AVStrMiniRemoveEvent, stream.avstrminiremoveevent
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - PFNKSREMOVEEVENT
 - ks/PFNKSREMOVEEVENT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ks.h
api_name:
 - AVStrMiniRemoveEvent
---

# PFNKSREMOVEEVENT callback function


## -description

An AVStream minidriver's *AVStrMiniRemoveEvent* routine is called when a client requests to be removed from the notification queue for an event. This routine is optional.

## -parameters

### -param FileObject 

[in]
Pointer to the file object for which to remove the event.

### -param EventEntry 

[in]
Pointer to an AVStream-generated [KSEVENT_ENTRY](./ns-ks-_ksevent_entry.md) structure.

## -remarks

The minidriver specifies this routine's address in the **RemoveHandler** member of a [KSEVENT_ITEM](./ns-ks-ksevent_item.md) structure. [Event Handling in AVStream](/windows-hardware/drivers/stream/event-handling-in-avstream) describes how the minidriver provides this structure to the class driver.

If the minidriver provides *AVStrMiniRemoveEvent* and either does not specify an **AddHandler** or specifies an **AddHandler** that calls **Ks***Xxx***AddEvent**, then the minidriver's *AVStrMiniRemoveEvent* must call [RemoveEntryList](../wdm/nf-wdm-removeentrylist.md) with a pointer to the LIST_ENTRY structure in the [KSEVENT_ENTRY](./ns-ks-_ksevent_entry.md) structure:

```cpp
&EventEntry -> ListEntry
```

Otherwise, your *AVStrMiniRemoveEvent* should reverse the steps taken in the **AddHandler**.

## -see-also

[AVStrMiniAddEvent](./nc-ks-pfnksaddevent.md)

[KSAUTOMATION_TABLE](./ns-ks-ksautomation_table_.md)

[KSEVENTDATA](./ns-ks-kseventdata.md)

[KSEVENT_ENTRY](./ns-ks-_ksevent_entry.md)

[KSEVENT_ITEM](./ns-ks-ksevent_item.md)

[KsFilterAddEvent](./nf-ks-ksfilteraddevent.md)

[KsFilterGenerateEvents](./nf-ks-ksfiltergenerateevents.md)

[KsPinAddEvent](./nf-ks-kspinaddevent.md)

[KsPinGenerateEvents](./nf-ks-kspingenerateevents.md)