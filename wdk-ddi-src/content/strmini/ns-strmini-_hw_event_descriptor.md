---
UID: NS:strmini._HW_EVENT_DESCRIPTOR
title: "_HW_EVENT_DESCRIPTOR"
author: windows-driver-content
description: When the class driver calls one of the minidriver's StrMiniEvent routines, it passes a pointer to an HW_EVENT_DESCRIPTOR structure to describe the event as enabled or disabled.
old-location: stream\hw_event_descriptor.htm
old-project: stream
ms.assetid: c0efec37-4897-4ece-9f53-4a62204e5af3
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: HW_EVENT_DESCRIPTOR, stream.hw_event_descriptor, strmini/HW_EVENT_DESCRIPTOR, PHW_EVENT_DESCRIPTOR, strclass-struct_ca0c15b2-17d1-4114-9765-5638dd81ca24.xml, strmini/PHW_EVENT_DESCRIPTOR, PHW_EVENT_DESCRIPTOR structure pointer [Streaming Media Devices], HW_EVENT_DESCRIPTOR structure [Streaming Media Devices], _HW_EVENT_DESCRIPTOR, *PHW_EVENT_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: strmini.h
req.include-header: Strmini.h
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
-	strmini.h
apiname:
-	HW_EVENT_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: "*PHW_EVENT_DESCRIPTOR, HW_EVENT_DESCRIPTOR"
req.product: Windows 10 or later.
---

# _HW_EVENT_DESCRIPTOR structure


## -description


When the class driver calls one of the minidriver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568457">StrMiniEvent</a> routines, it passes a pointer to an HW_EVENT_DESCRIPTOR structure to describe the event as enabled or disabled. 


## -syntax


````
typedef struct _HW_EVENT_DESCRIPTOR {
  BOOLEAN        Enable;
  PKSEVENT_ENTRY EventEntry;
  PKSEVENTDATA   EventData;
  union {
    struct _HW_STREAM_OBJECT  *StreamObject;
    struct _HW_DEVICE_EXTENSION  *DeviceExtension;
  };
  ULONG          EnableEventSetIndex;
#if (NTDDI_VERSION >= NTDDI_WINXP)
  PVOID          HwInstanceExtension;
  ULONG          Reserved;
#else 
  ULONG          Reserved[2];
#endif 
} HW_EVENT_DESCRIPTOR, *PHW_EVENT_DESCRIPTOR;
````


## -struct-fields




### -field StreamObject

Points to the <a href="..\strmini\ns-strmini-_hw_stream_object.md">HW_STREAM_OBJECT</a> for the stream that owns the event that the class driver is enabling/disabling, or <b>NULL</b> if the event belongs to the driver as a whole.


### -field DeviceExtension

Points to the minidriver's device extension.


### -field Enable

This is set to <b>TRUE</b> for an enabled event, and <b>FALSE</b> for a disabled event.


### -field EventEntry

Points to the <a href="..\ks\ns-ks-_ksevent_entry.md">KSEVENT_ENTRY</a> structure that describes this event.


### -field EventData

Points to the <a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a> structure that describes this instance of the event.


### -field EnableEventSetIndex

For stream events, this specifies the index of the event set within the <b>StreamEventsArray</b> member of the stream's <a href="..\strmini\ns-strmini-_hw_stream_information.md">HW_STREAM_INFORMATION</a> structure.

For device events, this specifies the index of the event set within the <b>DeviceEventsArray</b> member of the minidriver's <a href="..\strmini\ns-strmini-_hw_stream_header.md">HW_STREAM_HEADER</a> structure.


### -field HwInstanceExtension

Pointer to the minidriver's instance extension. The minidriver may use this buffer to record private information global to this instance of the minidriver. The minidriver sets the size of this buffer in the <a href="..\strmini\ns-strmini-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a> structure it passes when it registers itself via <a href="https://msdn.microsoft.com/library/windows/hardware/ff568263">StreamClassRegisterMinidriver</a>.




### -field Reserved

Reserved for system use. Do not use.


#### - Reserved[2]

Reserved for system use. Do not use.

