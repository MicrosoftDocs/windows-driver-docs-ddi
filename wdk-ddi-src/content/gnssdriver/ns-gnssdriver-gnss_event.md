---
UID: NS:gnssdriver.__unnamed_struct_34
title: GNSS_EVENT (gnssdriver.h)
description: This structure defines the information required for a GNSS event.
old-location: gnss\gnss_event.htm
tech.root: gnss
ms.assetid: FECF2444-CFF7-4B4D-AC3A-D3DD9B045AFD
ms.date: 02/15/2018
ms.keywords: "*PGNSS_EVENT, GNSS_EVENT, GNSS_EVENT structure [Sensor Devices], PGNSS_EVENT, PGNSS_EVENT structure pointer [Sensor Devices], gnss.gnss_event, gnssdriver/GNSS_EVENT, gnssdriver/PGNSS_EVENT"
ms.topic: struct
f1_keywords:
 - "gnssdriver/GNSS_EVENT"
req.header: gnssdriver.h
req.include-header: 
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- gnssdriver.h
api_name:
- GNSS_EVENT
product:
- Windows
targetos: Windows
req.typenames: GNSS_EVENT, *PGNSS_EVENT
---

# GNSS_EVENT structure


## -description


This structure defines the information required for a  GNSS event.


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

 


### -field FixData

This structure is filled if EventType is GNSS_Fix_Available.


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

 




#### - CustomData[ANYSIZE_ARRAY]

Custom data field.


#### - Unused[512]

Padding buffer.


## -remarks



The GNSS driver sends solicited and unsolicited notifications to the GNSS adapter. This is done through a common event protocol between the driver and the GNSS adapter. The adapter registers for one or more types of events and this ensures that one or more I/O requests are always pending for the driver to send the notification up to the adapter. The driver completes the I/O request on the pending IRP and this causes the notification to flow up to the adapter. The adapter creates one or more I/O requests to listen for further notifications.

 It is recommended (but not required) that the driver uses separate queues for managing different types of event. Separation of queues allows the driver to process certain types of events in parallel.

The notification model allows for adding custom or vendor-specific events in the future that can optionally be processed by a custom GNSS helper component. The GNSS adapter can act as a broker between the driver and the helper component and ensures that the commands and data are marshaled between these two components back and forth.

Each event type has associate event-specific data that the GNSS adapter uses to determine how to process the specific event. For example, for assistance requirements (AGNSS), the adapter injects the needed assistance data. For data-retrieval type event, the adapter processes and sends the data to an upper layer. Subsequently the adapter re-registers for same event with the driver through well-defined IOCTLs. All events follow the same overall data-structure.

Events can be of various types. Certain events occur as a result of a previous request initiated by the driver (for example, a start fix request). Certain events are raised for informational purpose. Assistance events are raised when the driver requires the adapter to inject specific assistance data.



