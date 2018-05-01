---
UID: NS:drmk.KSDRMAUDIOSTREAM_CONTENTID
title: KSDRMAUDIOSTREAM_CONTENTID
author: windows-driver-content
description: The KSDRMAUDIOSTREAM_CONTENTID structure specifies the DRM content ID and DRM content rights for a KSPROPERTY_DRMAUDIOSTREAM_CONTENTIDset-property request.
old-location: audio\ksdrmaudiostream_contentid.htm
old-project: audio
ms.assetid: d11be514-2a45-407e-884a-66f6f503f57a
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*PKSDRMAUDIOSTREAM_CONTENTID, KSDRMAUDIOSTREAM_CONTENTID, KSDRMAUDIOSTREAM_CONTENTID structure [Audio Devices], PKSDRMAUDIOSTREAM_CONTENTID, PKSDRMAUDIOSTREAM_CONTENTID structure pointer [Audio Devices], aud-prop_451e4ef3-53c7-4be2-a59c-efd34633c007.xml, audio.ksdrmaudiostream_contentid, drmk/KSDRMAUDIOSTREAM_CONTENTID, drmk/PKSDRMAUDIOSTREAM_CONTENTID"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: drmk.h
req.include-header: Drmk.h
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
-	drmk.h
api_name:
-	KSDRMAUDIOSTREAM_CONTENTID
product: Windows
targetos: Windows
req.typenames: KSDRMAUDIOSTREAM_CONTENTID, *PKSDRMAUDIOSTREAM_CONTENTID
---

# KSDRMAUDIOSTREAM_CONTENTID structure


## -description


The KSDRMAUDIOSTREAM_CONTENTID structure specifies the DRM content ID and DRM content rights for a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>set-property request.


## -struct-fields




### -field ContentId

Specifies the DRM content ID. This member identifies a protected KS audio stream.


### -field DrmRights

Specifies the DRM content rights assigned to the stream. This member is a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff536355">DRMRIGHTS</a> structure.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536355">DRMRIGHTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>
 

 

