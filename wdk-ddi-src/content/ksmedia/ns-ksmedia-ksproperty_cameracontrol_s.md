---
UID: NS:ksmedia.KSPROPERTY_CAMERACONTROL_S
title: KSPROPERTY_CAMERACONTROL_S (ksmedia.h)
description: The KSPROPERTY_CAMERACONTROL_S structure describes filter-based properties in the PROPSETID_VIDCAP_CAMERACONTROL property set.
tech.root: stream
ms.date: 03/14/2023
keywords: ["KSPROPERTY_CAMERACONTROL_S structure"]
ms.keywords: "*PKSPROPERTY_CAMERACONTROL_S, KSPROPERTY_CAMERACONTROL_S, KSPROPERTY_CAMERACONTROL_S structure [Streaming Media Devices], PKSPROPERTY_CAMERACONTROL_S, PKSPROPERTY_CAMERACONTROL_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_CAMERACONTROL_S, ksmedia/PKSPROPERTY_CAMERACONTROL_S, stream.ksproperty_cameracontrol_s, vidcapstruct_bfabf468-24f0-4acb-b064-229b3eea7df3.xml"
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
targetos: Windows
req.typenames: KSPROPERTY_CAMERACONTROL_S, *PKSPROPERTY_CAMERACONTROL_S
f1_keywords:
 - PKSPROPERTY_CAMERACONTROL_S
 - ksmedia/PKSPROPERTY_CAMERACONTROL_S
 - KSPROPERTY_CAMERACONTROL_S
 - ksmedia/KSPROPERTY_CAMERACONTROL_S
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - PKSPROPERTY_CAMERACONTROL_S
 - KSPROPERTY_CAMERACONTROL_S
---

## -description

The **KSPROPERTY_CAMERACONTROL_S** structure describes filter-based properties in the [PROPSETID_VIDCAP_CAMERACONTROL](/windows-hardware/drivers/stream/propsetid-vidcap-cameracontrol) property set.

## -struct-fields

### -field Property

Specifies an initialized [KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure) structure that describes the property set, property ID, and request type.

### -field Value

Specifies the value of the property. This member is read/write.

### -field Flags

Indicates, for Get requests, the current setting for the specified property from the values listed below. Indicates, for Set requests, the desired setting for the specified property from the values listed below. This member can be set to one of the following values that are defined in *ksmedia.h*:

| Flag | Meaning |
|---|---|
| KSPROPERTY_CAMERACONTROL_FLAGS_MANUAL | Indicates that the setting is controlled manually. |
| KSPROPERTY_CAMERACONTROL_FLAGS_AUTO | Indicates that the setting is controlled automatically. |
| KSPROPERTY_CAMERACONTROL_FLAGS_ABSOLUTE | Indicates that the setting is in absolute values. |
| KSPROPERTY_CAMERACONTROL_FLAGS_RELATIVE | Indicates that the setting is in relative values. |

### -field Capabilities

Indicates the minidriver's camera control capabilities for the specified property. This member is read-only. This member can be set to one of the following values that are defined in *ksmedia.h*:

| Flag | Meaning |
|---|---|
| KSPROPERTY_CAMERACONTROL_FLAGS_MANUAL | Indicates that the device can be controlled manually. |
| KSPROPERTY_CAMERACONTROL_FLAGS_AUTO | Indicates that the device can be controlled automatically. |
| KSPROPERTY_CAMERACONTROL_FLAGS_ABSOLUTE | Indicates that the device settings are in absolute values. |
| KSPROPERTY_CAMERACONTROL_FLAGS_RELATIVE | Indicates that the device settings are in relative values. |

## -see-also

[KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure)

[**KSPROPERTY_CAMERACONTROL_NODE_S**](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_cameracontrol_node_s)

[PROPSETID_VIDCAP_CAMERACONTROL](/windows-hardware/drivers/stream/propsetid-vidcap-cameracontrol)
