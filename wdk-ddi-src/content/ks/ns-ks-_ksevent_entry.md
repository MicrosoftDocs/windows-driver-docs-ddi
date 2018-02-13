---
UID: NS:ks._KSEVENT_ENTRY
title: "_KSEVENT_ENTRY"
author: windows-driver-content
description: The kernel streaming subsystem uses the KSEVENT_ENTRY structure to describe how an event should be triggered.
old-location: stream\ksevent_entry.htm
old-project: stream
ms.assetid: 2d246109-839d-46fd-9898-9e059b803790
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: "_KSEVENT_ENTRY, ks-struct_1c40526b-bc37-4f6b-a1e1-b0e710238156.xml, KSEVENT_ENTRY, *PKSEVENT_ENTRY, KSEVENT_ENTRY structure [Streaming Media Devices], stream.ksevent_entry, ks/KSEVENT_ENTRY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ks.h
apiname:
-	KSEVENT_ENTRY
product: Windows
targetos: Windows
req.typenames: "*PKSEVENT_ENTRY, KSEVENT_ENTRY"
---

# _KSEVENT_ENTRY structure


## -description


The kernel streaming subsystem uses the KSEVENT_ENTRY structure to describe how an event should be triggered.


## -syntax


````
typedef struct _KSEVENT_ENTRY {
  LIST_ENTRY        ListEntry;
  PVOID             Object;
  union {
    PKSDPC_ITEM    DpcItem;
    PKSBUFFER_ITEM BufferItem;
  };
  PKSEVENTDATA      EventData;
  const KSEVENT_SET NotificationType;
  const             *EventSet;
  KSEVENT_ITEM      *EventItem;
  PFILE_OBJECT      FileObject;
  ULONG             SemaphoreAdjustment;
  ULONG             Reserved;
  ULONG             Flags;
} KSEVENT_ENTRY;
````


## -struct-fields




### -field ListEntry


### -field Object


### -field DpcItem


### -field BufferItem


### -field EventData


### -field NotificationType


### -field EventSet


### -field EventItem


### -field FileObject


### -field SemaphoreAdjustment


### -field Reserved


### -field Flags


## -remarks



Drivers that do not provide an <a href="..\ks\nc-ks-pfnksremoveevent.md">AVStrMiniRemoveEvent</a> handler should treat this as an opaque data structure.

For more information, see <a href="https://msdn.microsoft.com/7add2055-8d3f-432d-8aa1-44459ac197dd">Event Handling in AVStream</a>.



