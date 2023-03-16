---
UID: NS:ksmedia.KSPROPERTY_VIDEOPROCAMP_NODE_S
title: KSPROPERTY_VIDEOPROCAMP_NODE_S (ksmedia.h)
description: The KSPROPERTY_VIDEOPROCAMP_NODE_S structure describes node-based property settings in the PROPSETID_VIDCAP_VIDEOPROCAMP property set.
tech.root: stream
ms.date: 03/14/2023
keywords: ["KSPROPERTY_VIDEOPROCAMP_NODE_S structure"]
ms.keywords: "*PKSPROPERTY_VIDEOPROCAMP_NODE_S, KSPROPERTY_VIDEOPROCAMP_NODE_S, KSPROPERTY_VIDEOPROCAMP_NODE_S structure [Streaming Media Devices], PKSPROPERTY_VIDEOPROCAMP_NODE_S, PKSPROPERTY_VIDEOPROCAMP_NODE_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_VIDEOPROCAMP_NODE_S, ksmedia/PKSPROPERTY_VIDEOPROCAMP_NODE_S, stream.ksproperty_videoprocamp_node_s, vidcapstruct_d7d544d4-dd33-4498-9104-c63fa5a48079.xml"
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
req.typenames: KSPROPERTY_VIDEOPROCAMP_NODE_S, *PKSPROPERTY_VIDEOPROCAMP_NODE_S
f1_keywords:
 - PKSPROPERTY_VIDEOPROCAMP_NODE_S
 - ksmedia/PKSPROPERTY_VIDEOPROCAMP_NODE_S
 - KSPROPERTY_VIDEOPROCAMP_NODE_S
 - ksmedia/KSPROPERTY_VIDEOPROCAMP_NODE_S
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - PKSPROPERTY_VIDEOPROCAMP_NODE_S
 - KSPROPERTY_VIDEOPROCAMP_NODE_S
---

## -description

The **KSPROPERTY_VIDEOPROCAMP_NODE_S** structure describes node-based property settings in the [PROPSETID_VIDCAP_VIDEOPROCAMP](/windows-hardware/drivers/stream/propsetid-vidcap-videoprocamp) property set.

## -struct-fields

### -field NodeProperty

Specifies an initialized [**KSP_NODE**](/windows-hardware/drivers/ddi/ks/ns-ks-ksp_node) structure that describes the node, property set, property ID, and request type.

### -field Value

Specifies the value of a request. For Set requests, the minidriver should set the property specified in **Property** to this value. For Get requests, the minidriver should return the value of the property specified in **Property**.

### -field Flags

Specifies the flags of a request. For Set requests, this value indicates the desired setting. For Get requests, this value contains the current setting. This member can be set to one of the values that are defined in *ksmedia.h*:

| Flag | Meaning |
|---|---|
| KSPROPERTY_VIDEOPROCAMP_FLAGS_MANUAL | Indicates that the property is to be adjusted manually. |
| KSPROPERTY_VIDEOPROCAMP_FLAGS_AUTO | Indicates that the property is to be adjusted automatically. |

### -field Capabilities

Specifies the capabilities of a property. This member has meaning only for Get requests. The minidriver should return the capabilities of the VideoProcAmp with respect to the property specified in **Property**. This member should be set to one of the following values:

| Value | Meaning |
|---|---|
| KSPROPERTY_VIDEOPROCAMP_FLAGS_MANUAL | The device supports manual setting of the specified property. |
| KSPROPERTY_VIDEOPROCAMP_FLAGS_AUTO | The device supports automatic setting of the specified property. |

## -see-also

[**KSPROPERTY_VIDEOPROCAMP_S**](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_videoprocamp_s)
