---
UID: NS:ksmedia.KSPROPERTY_CAMERACONTROL_S2
title: KSPROPERTY_CAMERACONTROL_S2 (ksmedia.h)
description: The KSPROPERTY_CAMERACONTROL_S2 structure describes filter-based properties in the PROPSETID_VIDCAP_CAMERACONTROL property set that use two values at the same time.
tech.root: stream
ms.date: 03/14/2023
keywords: ["KSPROPERTY_CAMERACONTROL_S2 structure"]
ms.keywords: "*PKSPROPERTY_CAMERACONTROL_S2, KSPROPERTY_CAMERACONTROL_S2, KSPROPERTY_CAMERACONTROL_S2 structure [Streaming Media Devices], PKSPROPERTY_CAMERACONTROL_S2, PKSPROPERTY_CAMERACONTROL_S2 structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_CAMERACONTROL_S2, ksmedia/PKSPROPERTY_CAMERACONTROL_S2, stream.ksproperty_cameracontrol_s2, vidcapstruct_8ffb951a-dfed-4871-b8f8-36e975884c1e.xml"
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
req.typenames: KSPROPERTY_CAMERACONTROL_S2, *PKSPROPERTY_CAMERACONTROL_S2
f1_keywords:
 - PKSPROPERTY_CAMERACONTROL_S2
 - ksmedia/PKSPROPERTY_CAMERACONTROL_S2
 - KSPROPERTY_CAMERACONTROL_S2
 - ksmedia/KSPROPERTY_CAMERACONTROL_S2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - PKSPROPERTY_CAMERACONTROL_S2
 - KSPROPERTY_CAMERACONTROL_S2
---

## -description

The **KSPROPERTY_CAMERACONTROL_S2** structure describes filter-based properties in the [PROPSETID_VIDCAP_CAMERACONTROL](/windows-hardware/drivers/stream/propsetid-vidcap-cameracontrol) property set that use two values at the same time.

## -struct-fields

### -field Property

Specifies an initialized [KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure) structure that describes the property set, property ID, and request type.

### -field Value1

Specifies the first value of the property. This member is read/write.

### -field Flags

Indicates, for get requests, the current setting for the specified property from the values listed below. Indicates, for set requests, the desired setting for the specified property from the values listed below. This member can be set to one of the following values that are defined in *ksmedia.h*:

| Flag | Meaning |
|---|---|
| KSPROPERTY_CAMERACONTROL_FLAGS_MANUAL | Indicates that the setting is controlled manually |
| KSPROPERTY_CAMERACONTROL_FLAGS_AUTO | Indicates that the setting is controlled automatically |
| KSPROPERTY_CAMERACONTROL_FLAGS_ABSOLUTE | Indicates that the setting is in absolute values |
| KSPROPERTY_CAMERACONTROL_FLAGS_RELATIVE | Indicates that the setting is in relative values |

### -field Capabilities

Indicates the minidriver's camera control capabilities for the specified property. This member is read-only. This member can be set to one of the following values that are defined in *ksmedia.h*:

| Flag | Meaning |
|---|---|
| KSPROPERTY_CAMERACONTROL_FLAGS_MANUAL | Indicates that the device can be controlled manually |
| KSPROPERTY_CAMERACONTROL_FLAGS_AUTO | Indicates that the device can be controlled automatically |
| KSPROPERTY_CAMERACONTROL_FLAGS_ABSOLUTE | Indicates that the device settings are in absolute values |
| KSPROPERTY_CAMERACONTROL_FLAGS_RELATIVE | Indicates that the device settings are in relative values |

### -field Value2

Specifies the second value of the property. This member is read/write.

## -remarks

This structure is used by [KSPROPERTY_CAMERACONTROL_PANTILT](/windows-hardware/drivers/stream/ksproperty-cameracontrol-pantilt) and [KSPROPERTY_CAMERACONTROL_PANTILT_RELATIVE](/windows-hardware/drivers/stream/ksproperty-cameracontrol-pantilt-relative) for filter-based get/set property requests.
