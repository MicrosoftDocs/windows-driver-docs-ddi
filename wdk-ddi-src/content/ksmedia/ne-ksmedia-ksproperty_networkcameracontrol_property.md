---
UID: NE:ksmedia.__unnamed_enum_93
title: KSPROPERTY_NETWORKCAMERACONTROL_PROPERTY (ksmedia.h)
description: The KSPROPERTY_NETWORKCAMERACONTROL_PROPERTY enumeration defines the network camera control properties.
tech.root: stream
ms.date: 07/27/2020
ms.topic: enum
ms.keywords: KSPROPERTY_NETWORKCAMERACONTROL_PROPERTY
f1_keywords:
- "ksmedia/KSPROPERTY_NETWORKCAMERACONTROL_PROPERTY"
 - "KSPROPERTY_NETWORKCAMERACONTROL_PROPERTY"
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
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ksmedia.h
api_name: 
- KSPROPERTY_NETWORKCAMERACONTROL_PROPERTY
dev_langs:
- c++
targetos: Windows
---

# KSPROPERTY_NETWORKCAMERACONTROL_PROPERTY enumeration

## -description

The **KSPROPERTY_NETWORKCAMERACONTROL_PROPERTY** enumeration defines the network camera control properties.

## -enum-fields

### -field KSPROPERTY_NETWORKCAMERACONTROL_NTP

Set an NTP server on an Onvif protocol camera.

### -field KSPROPERTY_NETWORKCAMERACONTROL_URI

Acquire the stream URI payload from a Onvif protocol camera. The payload is a wide character null-terminated string representing the streaming URI (RSTP/HTTP URI).

## -see-also

[KSPROPERTY_NETWORKCAMERACONTROL_NTPINFO_HEADER](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksmedia/ns-ksmedia-ksproperty_networkcameracontrol_ntpinfo_header)

[KSPROPERTY_NETWORKCAMERACONTROL_NTPINFO_TYPE](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksmedia/ne-ksmedia-ksproperty_networkcameracontrol_ntpinfo_type)
