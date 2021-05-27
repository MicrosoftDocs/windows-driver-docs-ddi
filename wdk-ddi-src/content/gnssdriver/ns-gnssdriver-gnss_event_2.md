---
UID: NS:gnssdriver.__unnamed_struct_39
title: GNSS_EVENT_2 (gnssdriver.h)
ms.date: 04/05/2021
targetos: Windows
tech.root: gnss
description: The GNSS_EVENT_2 structure defines the information required for a GNSS event.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: gnssdriver.h
req.include-header: Gnssdriver.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt:
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: GNSS_EVENT_2, *PGNSS_EVENT_2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - PGNSS_EVENT_2
 - GNSS_EVENT_2
f1_keywords:
 - PGNSS_EVENT_2
 - gnssdriver/PGNSS_EVENT_2
 - GNSS_EVENT_2
 - gnssdriver/GNSS_EVENT_2
dev_langs:
 - c++
---

## -description

The **GNSS_EVENT_2** structure defines the information required for a GNSS event.

## -struct-fields

### -field Size

Structure size.

### -field Version

Version number.

### -field EventType

Event type.

Depending on the event type, a specific data element of the union will be filled.

### -field EventDataSize

The size of the event data union contained in this event.

The GNSS driver must fill in appropriate size to avoid excessive data-copy between the layers. The GNSS adapter will access only the initial bytes of the event data, as specified by this element.

### -field Unused

Unused.

### -field FixData

This structure is filled if EventType is GNSS_Fix_Available.

### -field FixData2

### -field AgnssRequest

This structure is filled if EventType is GNSS_Require_Agnss.

### -field NiRequest

This structure is filled if EventType is GNSS_Event_Ni.

### -field ErrorInformation

This structure is filled if EventType is GNSS_Error.

### -field NmeaData

This structure is filled if EventType is GNSS_Event_NmeaData.

### -field GeofenceAlertData

This structure is filled if EventType is GNSS_Event_GeofenceAlertData.

### -field BreadcrumbAlertData

This structure contains alert information for when the breadcrumb buffer has reached a level where OS read operations should be performed.

### -field GeofencesTrackingStatus

This structure is filled if EventType is GNSS_Event_GeofencesTrackingStatus.

### -field DriverRequestData

This structure is filled if EventType is GNSS_Event_DriverRequest.

### -field CustomData

Custom data field.

## -remarks

## -see-also
