---
UID: NS:ksmedia.KSPROPERTY_SELECTOR_S
title: KSPROPERTY_SELECTOR_S
author: windows-driver-content
description: The KSPROPERTY_SELECTOR_S structure describes filter-based property settings in the PROPSETID_VIDCAP_SELECTOR property set.
old-location: stream\ksproperty_selector_s.htm
tech.root: stream
ms.assetid: cc9928b7-fab2-44c1-8613-3a94b5e8dcab
ms.date: 4/23/2018
ms.keywords: "*PKSPROPERTY_SELECTOR_S, KSPROPERTY_SELECTOR_S, KSPROPERTY_SELECTOR_S structure [Streaming Media Devices], PKSPROPERTY_SELECTOR_S, PKSPROPERTY_SELECTOR_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_SELECTOR_S, ksmedia/PKSPROPERTY_SELECTOR_S, stream.ksproperty_selector_s, vidcapstruct_7e180fae-5237-4b71-8719-7d3c5ee66592.xml"
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KSPROPERTY_SELECTOR_S
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_SELECTOR_S, *PKSPROPERTY_SELECTOR_S
---

# KSPROPERTY_SELECTOR_S structure


## -description


The KSPROPERTY_SELECTOR_S structure describes filter-based property settings in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567810">PROPSETID_VIDCAP_SELECTOR</a> property set.


## -struct-fields




### -field Property

Specifies an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff566720">KSP_NODE</a> structure that describes the node, property set, property ID, and request type.


### -field Value

Specifies the value of a request. For Set requests, the minidriver should set the property specified in <b>Property</b> to this value. For Get requests, the minidriver should return the value of the property specified in <b>Property</b>.


### -field Flags

Specifies the flags of a request. For Set requests, this value indicates the desired setting. For Get requests, this value contains the current setting.


### -field Capabilities

Specifies the capabilities of a property. This member has meaning only for Get requests. The minidriver should return the capabilities of the Selector with respect to the property specified in <b>Property</b>.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565217">KSPROPERTY_SELECTOR_NODE_S</a>
 

 

