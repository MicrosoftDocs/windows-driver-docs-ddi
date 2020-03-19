---
UID: NS:ksmedia.__unnamed_struct_62
title: KSNODEPROPERTY (ksmedia.h)
description: The KSNODEPROPERTY structure specifies a node and a property of that node.
old-location: audio\ksnodeproperty.htm
tech.root: audio
ms.assetid: bbcf7597-217a-499b-b0f2-deef1e85becc
ms.date: 04/30/2019
keywords: ["KSNODEPROPERTY structure"]
ms.keywords: "*PKSNODEPROPERTY, KSNODEPROPERTY, KSNODEPROPERTY structure [Audio Devices], PKSNODEPROPERTY, PKSNODEPROPERTY structure pointer [Audio Devices], aud-prop_7d1e6907-77f6-445d-ba5d-b94037b234f3.xml, audio.ksnodeproperty, ksmedia/KSNODEPROPERTY, ksmedia/PKSNODEPROPERTY"
f1_keywords:
 - "ksmedia/KSNODEPROPERTY"
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
- KSNODEPROPERTY
product:
- Windows
targetos: Windows
req.typenames: KSNODEPROPERTY, *PKSNODEPROPERTY
---

# KSNODEPROPERTY structure


## -description


The KSNODEPROPERTY structure specifies a node and a property of that node.


## -struct-fields




### -field Property

Specifies the property to get or set. This member is a structure of type <a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>.


### -field NodeId

Specifies the node ID. This member identifies the target node for the property request.


### -field Reserved

Reserved for internal use by operating system. Do not use.


## -remarks



This structure is identical to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksp_node">KSP_NODE</a>.

See the discussion of the KSNODEPROPERTY structure in <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/audio-property-requests">Audio Property Requests</a>.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksp_node">KSP_NODE</a>
 

 

