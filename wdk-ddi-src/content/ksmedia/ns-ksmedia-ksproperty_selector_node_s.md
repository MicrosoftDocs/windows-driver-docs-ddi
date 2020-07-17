---
UID: NS:ksmedia.__unnamed_struct_95
title: KSPROPERTY_SELECTOR_NODE_S (ksmedia.h)
description: The KSPROPERTY_SELECTOR_NODE_S structure describes node-based property settings in the PROPSETID_VIDCAP_SELECTOR property set.
old-location: stream\ksproperty_selector_node_s.htm
tech.root: stream
ms.assetid: 37dc9f4a-1e9c-42f2-8894-4972562f5898
ms.date: 04/30/2019
keywords: ["KSPROPERTY_SELECTOR_NODE_S structure"]
ms.keywords: "*PKSPROPERTY_SELECTOR_NODE_S, KSPROPERTY_SELECTOR_NODE_S, KSPROPERTY_SELECTOR_NODE_S structure [Streaming Media Devices], PKSPROPERTY_SELECTOR_NODE_S, PKSPROPERTY_SELECTOR_NODE_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_SELECTOR_NODE_S, ksmedia/PKSPROPERTY_SELECTOR_NODE_S, stream.ksproperty_selector_node_s, vidcapstruct_f7f566f9-2eea-44f5-8a4b-33769d99576f.xml"
f1_keywords:
 - "ksmedia/KSPROPERTY_SELECTOR_NODE_S"
 - "KSPROPERTY_SELECTOR_NODE_S"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ksmedia.h
api_name:
- KSPROPERTY_SELECTOR_NODE_S
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_SELECTOR_NODE_S, *PKSPROPERTY_SELECTOR_NODE_S
---

# KSPROPERTY_SELECTOR_NODE_S structure


## -description


The KSPROPERTY_SELECTOR_NODE_S structure describes node-based property settings in the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/propsetid-vidcap-selector">PROPSETID_VIDCAP_SELECTOR</a> property set.


## -struct-fields




### -field NodeProperty

Specifies an initialized <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksp_node">KSP_NODE</a> structure that describes the node, property set, property ID, and request type.


### -field Value

Specifies the value of a request. For Set requests, the minidriver should set the property specified in <b>Property</b> to this value. For Get requests, the minidriver should return the value of the property specified in <b>Property</b>.


### -field Flags

Specifies the flags of a request. For Set requests, this value indicates the desired setting. For Get requests, this value contains the current setting.


### -field Capabilities

Specifies the capabilities of a property. This member has meaning only for Get requests. The minidriver should return the capabilities of the Selector with respect to the property specified in <b>Property</b>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_selector_s">KSPROPERTY_SELECTOR_S</a>
 

 

