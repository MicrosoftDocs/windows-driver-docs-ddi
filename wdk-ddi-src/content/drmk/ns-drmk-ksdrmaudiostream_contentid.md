---
UID: NS:drmk.KSDRMAUDIOSTREAM_CONTENTID
title: KSDRMAUDIOSTREAM_CONTENTID (drmk.h)
description: The KSDRMAUDIOSTREAM_CONTENTID structure specifies the DRM content ID and DRM content rights for a KSPROPERTY_DRMAUDIOSTREAM_CONTENTIDset-property request.
old-location: audio\ksdrmaudiostream_contentid.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["KSDRMAUDIOSTREAM_CONTENTID structure"]
ms.keywords: "*PKSDRMAUDIOSTREAM_CONTENTID, KSDRMAUDIOSTREAM_CONTENTID, KSDRMAUDIOSTREAM_CONTENTID structure [Audio Devices], PKSDRMAUDIOSTREAM_CONTENTID, PKSDRMAUDIOSTREAM_CONTENTID structure pointer [Audio Devices], aud-prop_451e4ef3-53c7-4be2-a59c-efd34633c007.xml, audio.ksdrmaudiostream_contentid, drmk/KSDRMAUDIOSTREAM_CONTENTID, drmk/PKSDRMAUDIOSTREAM_CONTENTID"
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
targetos: Windows
req.typenames: KSDRMAUDIOSTREAM_CONTENTID, *PKSDRMAUDIOSTREAM_CONTENTID
f1_keywords:
 - PKSDRMAUDIOSTREAM_CONTENTID
 - drmk/PKSDRMAUDIOSTREAM_CONTENTID
 - KSDRMAUDIOSTREAM_CONTENTID
 - drmk/KSDRMAUDIOSTREAM_CONTENTID
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - drmk.h
api_name:
 - PKSDRMAUDIOSTREAM_CONTENTID
 - KSDRMAUDIOSTREAM_CONTENTID
---

# KSDRMAUDIOSTREAM_CONTENTID structure


## -description

The KSDRMAUDIOSTREAM_CONTENTID structure specifies the DRM content ID and DRM content rights for a <a href="/previous-versions/ff537351(v=vs.85)">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>set-property request.

## -struct-fields

### -field ContentId

Specifies the DRM content ID. This member identifies a protected KS audio stream.

### -field DrmRights

Specifies the DRM content rights assigned to the stream. This member is a pointer to a <a href="/windows-hardware/drivers/ddi/drmk/ns-drmk-tagdrmrights">DRMRIGHTS</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/drmk/ns-drmk-tagdrmrights">DRMRIGHTS</a>



<a href="/previous-versions/ff537351(v=vs.85)">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>

