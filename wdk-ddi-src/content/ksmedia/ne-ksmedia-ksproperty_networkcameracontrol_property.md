---
UID: NE:ksmedia.KSPROPERTY_NETWORKCAMERACONTROL_PROPERTY
title: KSPROPERTY_NETWORKCAMERACONTROL_PROPERTY (ksmedia.h)
description: The KSPROPERTY_NETWORKCAMERACONTROL_PROPERTY enumeration defines the network camera control properties.
tech.root: stream
ms.date: 03/08/2022
ms.keywords: KSPROPERTY_NETWORKCAMERACONTROL_PROPERTY
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.construct-type: structure
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: KSPROPERTY_NETWORKCAMERACONTROL_PROPERTY
targetos: Windows
f1_keywords:
 - KSPROPERTY_NETWORKCAMERACONTROL_PROPERTY
 - ksmedia/KSPROPERTY_NETWORKCAMERACONTROL_PROPERTY
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSPROPERTY_NETWORKCAMERACONTROL_PROPERTY
---

## -description

The **KSPROPERTY_NETWORKCAMERACONTROL_PROPERTY** enumeration defines the network camera control properties.

## -enum-fields

### -field KSPROPERTY_NETWORKCAMERACONTROL_NTP

Set an NTP server on an Onvif protocol camera.

### -field KSPROPERTY_NETWORKCAMERACONTROL_URI

Acquire the stream URI payload from a Onvif protocol camera. The payload is a wide character null-terminated string representing the streaming URI (RSTP/HTTP URI).

### -field KSPROPERTY_NETWORKCAMERACONTROL_METADATA

Enumerates the network camera control metadata property.

### -field KSPROPERTY_NETWORKCAMERACONTROL_EVENTTOPICS_XML

Enumerates the network camera control event topics XML property.

## -remarks

## -see-also

[KSPROPERTY_NETWORKCAMERACONTROL_EVENTTOPICS_XML](/windows-hardware/drivers/stream/ksproperty-networkcameracontrol-eventtopics-xml)

[KSPROPERTY_NETWORKCAMERACONTROL_METADATA](/windows-hardware/drivers/stream/ksproperty-networkcameracontrol-metadata)

[KSPROPERTYSETID_NetworkCameraControl](/windows-hardware/drivers/stream/kspropertysetid-networkcameracontrol)

[KSPROPERTY_NETWORKCAMERACONTROL_NTP](/windows-hardware/drivers/stream/ksproperty-networkcameracontrol-ntp)

[KSPROPERTY_NETWORKCAMERACONTROL_URI](/windows-hardware/drivers/stream/ksproperty-networkcameracontrol-uri)

[KSPROPERTY_NETWORKCAMERACONTROL_EVENT_INFO](ns-ksmedia-ksproperty_networkcameracontrol_event_info.md)

[KSPROPERTY_NETWORKCAMERACONTROL_METADATA_INFO](ns-ksmedia-ksproperty_networkcameracontrol_metadata_info.md)

[KSPROPERTY_NETWORKCAMERACONTROL_NTPINFO_HEADER](ns-ksmedia-ksproperty_networkcameracontrol_ntpinfo_header.md)

[KSPROPERTY_NETWORKCAMERACONTROL_NTPINFO_TYPE](ne-ksmedia-ksproperty_networkcameracontrol_ntpinfo_type.md)

