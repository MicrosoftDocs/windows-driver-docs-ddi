---
UID: NS:ksmedia.KSPROPERTY_CAMERACONTROL_NODE_S
title: KSPROPERTY_CAMERACONTROL_NODE_S (ksmedia.h)
description: The KSPROPERTY_CAMERACONTROL_NODE_S structure describes node-based properties in the PROPSETID_VIDCAP_CAMERACONTROL property set. This structure specifies property values in requests to the USB Video Class driver.
tech.root: stream
ms.date: 03/10/2023
keywords: ["KSPROPERTY_CAMERACONTROL_NODE_S structure"]
ms.keywords: KSPROPERTY_CAMERACONTROL_NODE_S, KSPROPERTY_CAMERACONTROL_NODE_S structure [Streaming Media Devices], PKSPROPERTY_CAMERACONTROL_NODE_S, PKSPROPERTY_CAMERACONTROL_NODE_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_CAMERACONTROL_NODE_S, ksmedia/PKSPROPERTY_CAMERACONTROL_NODE_S, stream.ksproperty_cameracontrol_node_s, vidcapstruct_fbe0c251-5c32-49b7-978c-67b52c920613.xml
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
req.typenames: KSPROPERTY_CAMERACONTROL_NODE_S, PKSPROPERTY_CAMERACONTROL_NODE_S
f1_keywords:
 - KSPROPERTY_CAMERACONTROL_NODE_S
 - ksmedia/KSPROPERTY_CAMERACONTROL_NODE_S
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSPROPERTY_CAMERACONTROL_NODE_S
---

## -description

The KSPROPERTY_CAMERACONTROL_NODE_S structure describes node-based properties in the [PROPSETID_VIDCAP_CAMERACONTROL](/windows-hardware/drivers/stream/propsetid-vidcap-cameracontrol) property set. This structure specifies property values in requests to the USB Video Class driver.

## -struct-fields

### -field NodeProperty

Specifies an initialized [KSP_NODE](/windows-hardware/drivers/ddi/ks/ns-ks-ksp_node) structure that describes the property set, property ID, request type, and node ID.

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

## -remarks

See related information about the [USB Video Class Driver](/windows-hardware/drivers/stream/usb-video-class-driver).

## -see-also

[KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure)

[KSPROPERTY_CAMERACONTROL_S](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_cameracontrol_s)

[PROPSETID_VIDCAP_CAMERACONTROL](/windows-hardware/drivers/stream/propsetid-vidcap-cameracontrol)
