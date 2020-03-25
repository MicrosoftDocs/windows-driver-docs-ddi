---
UID: NE:ksmedia.__unnamed_enum_92
title: KSPROPERTY_NETWORKCAMERACONTROL_NTPINFO_TYPE  (ksmedia.h)
author: windows-driver-content
description: The **KSPROPERTY_NETWORKCAMERACONTROL_NTPINFO_TYPE** enumeration defines the network camera control NTP types.
tech.root: stream
ms.author: windowsdriverdev
ms.date: 03/25/2020
ms.topic: enum
ms.keywords: KSPROPERTY_NETWORKCAMERACONTROL_NTPINFO_TYPE
f1_keywords:
- "ksmedia/KSPROPERTY_NETWORKCAMERACONTROL_NTPINFO_TYPE"
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
req.typenames: KSPROPERTY_NETWORKCAMERACONTROL_NTPINFO_TYPE
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ksmedia.h
api_name: 
- KSPROPERTY_NETWORKCAMERACONTROL_NTPINFO_TYPE
dev_langs:
- c++
product: 
- Windows
targetos: Windows
---

# KSPROPERTY_NETWORKCAMERACONTROL_NTPINFO_TYPE enumeration

## -description

The **KSPROPERTY_NETWORKCAMERACONTROL_NTPINFO_TYPE** enumeration defines the network camera control NTP types.

## -syntax

## -enum-fields

### -field KSPROPERTY_NETWORKCAMERACONTROL_NTPINFO_TYPE_DISABLE

Sets the camera into manual mode. The user can set the time on the camera manually.

### -field KSPROPERTY_NETWORKCAMERACONTROL_NTPINFO_TYPE_HOSTNTP

Sets the camera to use the same NTP server as is configured on the host.

### -field KSPROPERYT_NETWORKCAMERACONTROL_NTPINFO_TYPE_CUSTOM

Sets a specific custom NTP server on the camera.

## -remarks

If NTP is enabled on the camera, a get operation will return the name of the NTP server that is set on the Onvif protocol device.

If use of a NTP server is disabled on the camera, a get operation will return KSPROPERTY_NETWORKCAMERACONTROL_NTPINFO_TYPE_DISABLE.

## -see-also

[KSPROPERTY_NETWORKCAMERACONTROL_NTPINFO_HEADER](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksmedia/ns-ksmedia-ksproperty_networkcameracontrol_ntpinfo_header)

[KSPROPERTY_NETWORKCAMERACONTROL_PROPERTY](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksmedia/ne-ksmedia-ksproperty_networkcameracontrol_property)
