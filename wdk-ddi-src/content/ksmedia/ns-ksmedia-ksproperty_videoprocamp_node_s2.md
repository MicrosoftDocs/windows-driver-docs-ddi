---
UID: NS:ksmedia.KSPROPERTY_VIDEOPROCAMP_NODE_S2
title: KSPROPERTY_VIDEOPROCAMP_NODE_S2 (ksmedia.h)
description: The KSPROPERTY_VIDEOPROCAMP_NODE_S2 structure describes node-based property settings in the PROPSETID_VIDCAP_VIDEOPROCAMP property set that use two values at the same time.
tech.root: stream
ms.date: 03/14/2023
keywords: ["KSPROPERTY_VIDEOPROCAMP_NODE_S2 structure"]
ms.keywords: "*PKSPROPERTY_VIDEOPROCAMP_NODE_S2, KSPROPERTY_VIDEOPROCAMP_NODE_S2, KSPROPERTY_VIDEOPROCAMP_NODE_S2 structure [Streaming Media Devices], PKSPROPERTY_VIDEOPROCAMP_NODE_S2, PKSPROPERTY_VIDEOPROCAMP_NODE_S2 structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_VIDEOPROCAMP_NODE_S2, ksmedia/PKSPROPERTY_VIDEOPROCAMP_NODE_S2, stream.ksproperty_videoprocamp_node_s2, vidcapstruct_1876d4f4-15ae-4bcb-9f57-ed08ddf15411.xml"
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
req.typenames: KSPROPERTY_VIDEOPROCAMP_NODE_S2, *PKSPROPERTY_VIDEOPROCAMP_NODE_S2
f1_keywords:
 - PKSPROPERTY_VIDEOPROCAMP_NODE_S2
 - ksmedia/PKSPROPERTY_VIDEOPROCAMP_NODE_S2
 - KSPROPERTY_VIDEOPROCAMP_NODE_S2
 - ksmedia/KSPROPERTY_VIDEOPROCAMP_NODE_S2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - PKSPROPERTY_VIDEOPROCAMP_NODE_S2
 - KSPROPERTY_VIDEOPROCAMP_NODE_S2
---

## -description

The **KSPROPERTY_VIDEOPROCAMP_NODE_S2** structure describes node-based property settings in the [PROPSETID_VIDCAP_VIDEOPROCAMP](/windows-hardware/drivers/stream/propsetid-vidcap-videoprocamp) property set that use two values at the same time.

## -struct-fields

### -field NodeProperty

Specifies an initialized [**KSP_NODE**](/windows-hardware/drivers/ddi/ks/ns-ks-ksp_node) structure that describes the node, property set, property ID, and request type.

### -field Value1

Specifies the first value of a request. For set requests, the minidriver should set the property specified in **Property** to this value. For get requests, the minidriver should return the value of the property specified in **Property**.

### -field Flags

Specifies the flags of a request. For set requests, this value indicates the desired setting. For get requests, this value contains the current setting. This member can be set to one of the values that are defined in *ksmedia.h*:

| Value | Meaning |
|---|---|
| KSPROPERTY_VIDEOPROCAMP_FLAGS_MANUAL | Indicates that the property is to be adjusted manually |
| KSPROPERTY_VIDEOPROCAMP_FLAGS_AUTO | Indicates that the property is to be adjusted automatically |

### -field Capabilities

Specifies the capabilities of a property. This member has meaning only for get requests. The minidriver should return the capabilities of the video processing amplifier with respect to the property specified in **Property**. This member should be set to one of the following values:

| Value | Meaning |
|---|---|
| KSPROPERTY_VIDEOPROCAMP_FLAGS_MANUAL | The device supports manual setting of the specified property |
| KSPROPERTY_VIDEOPROCAMP_FLAGS_AUTO | The device supports automatic setting of the specified property |

### -field Value2

Specifies the second value of a request. For set requests, the minidriver should set the property specified in **Property** to this value. For get requests, the minidriver should return the value of the property specified in **Property**.

## -remarks

This structure is used by [KSPROPERTY_VIDEOPROCAMP_WHITEBALANCE_COMPONENT](/windows-hardware/drivers/stream/ksproperty-videoprocamp-whitebalance-component).
