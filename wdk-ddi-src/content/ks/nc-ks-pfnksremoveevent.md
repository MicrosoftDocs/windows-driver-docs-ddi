---
UID: NC:ks.PFNKSREMOVEEVENT
title: PFNKSREMOVEEVENT (ks.h)
description: An AVStream minidriver's AVStrMiniRemoveEvent routine is called when a client requests to be removed from the notification queue for an event. This routine is optional.
old-location: stream\avstrminiremoveevent.htm
tech.root: stream
ms.assetid: dee4ce19-9dc8-4728-855b-eadb5bca0fc2
ms.date: 04/23/2018
ms.keywords: AVStrMiniRemoveEvent, AVStrMiniRemoveEvent routine [Streaming Media Devices], PFNKSREMOVEEVENT, avstclbk_04bc810f-666a-4b24-9bc9-e203ebbbbf29.xml, ks/AVStrMiniRemoveEvent, stream.avstrminiremoveevent
f1_keywords:
 - "ks/AVStrMiniRemoveEvent"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ks.h
api_name:
- AVStrMiniRemoveEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNKSREMOVEEVENT callback function

## -description

An AVStream minidriver's *AVStrMiniRemoveEvent* routine is called when a client requests to be removed from the notification queue for an event. This routine is optional.

## -parameters

### -param FileObject [in]

Pointer to the file object for which to remove the event.

### -param *EventEntry [in]

Pointer to an AVStream-generated [KSEVENT_ENTRY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksevent_entry) structure.

## -remarks

The minidriver specifies this routine's address in the **RemoveHandler** member of a [KSEVENT_ITEM](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksevent_item) structure. [Event Handling in AVStream](https://docs.microsoft.com/windows-hardware/drivers/stream/event-handling-in-avstream) describes how the minidriver provides this structure to the class driver.

If the minidriver provides *AVStrMiniRemoveEvent* and either does not specify an **AddHandler** or specifies an **AddHandler** that calls **Ks***Xxx***AddEvent**, then the minidriver's *AVStrMiniRemoveEvent* must call [RemoveEntryList](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-removeentrylist) with a pointer to the LIST_ENTRY structure in the [KSEVENT_ENTRY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksevent_entry) structure:

```cpp
&EventEntry -> ListEntry
```

Otherwise, your *AVStrMiniRemoveEvent* should reverse the steps taken in the **AddHandler**.

## -see-also

[AVStrMiniAddEvent](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnksaddevent)

[KSAUTOMATION_TABLE](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksautomation_table_)

[KSEVENTDATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-kseventdata)

[KSEVENT_ENTRY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksevent_entry)

[KSEVENT_ITEM](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksevent_item)

[KsFilterAddEvent](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfilteraddevent)

[KsFilterGenerateEvents](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfiltergenerateevents)

[KsPinAddEvent](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspinaddevent)

[KsPinGenerateEvents](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspingenerateevents)
