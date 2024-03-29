---
UID: NS:ksmedia.KSRTAUDIO_HWREGISTER_PROPERTY
title: KSRTAUDIO_HWREGISTER_PROPERTY (ksmedia.h)
description: The KSRTAUDIO_HWREGISTRY_PROPERTY structure appends a register base address to a KSPROPERTY structure.
old-location: audio\ksrtaudio_hwregister_property.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["KSRTAUDIO_HWREGISTER_PROPERTY structure"]
ms.keywords: "*PKSRTAUDIO_HWREGISTER_PROPERTY, KSRTAUDIO_HWREGISTER_PROPERTY, KSRTAUDIO_HWREGISTER_PROPERTY structure [Audio Devices], PKSRTAUDIO_HWREGISTER_PROPERTY, PKSRTAUDIO_HWREGISTER_PROPERTY structure pointer [Audio Devices], aud-prop_d554442a-4677-4fc6-a305-ef02d5caffef.xml, audio.ksrtaudio_hwregister_property, ksmedia/KSRTAUDIO_HWREGISTER_PROPERTY, ksmedia/PKSRTAUDIO_HWREGISTER_PROPERTY"
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later Windows operating systems.
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
req.typenames: KSRTAUDIO_HWREGISTER_PROPERTY, *PKSRTAUDIO_HWREGISTER_PROPERTY
f1_keywords:
 - PKSRTAUDIO_HWREGISTER_PROPERTY
 - ksmedia/PKSRTAUDIO_HWREGISTER_PROPERTY
 - KSRTAUDIO_HWREGISTER_PROPERTY
 - ksmedia/KSRTAUDIO_HWREGISTER_PROPERTY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - PKSRTAUDIO_HWREGISTER_PROPERTY
 - KSRTAUDIO_HWREGISTER_PROPERTY
---

# KSRTAUDIO_HWREGISTER_PROPERTY structure


## -description

The KSRTAUDIO_HWREGISTRY_PROPERTY structure appends a register base address to a KSPROPERTY structure.  This structure is used by the client to request the hardware position register via <a href="/windows-hardware/drivers/audio/ksproperty-rtaudio-positionregister">KSPROPERTY_RTAUDIO_POSITIONREGISTER</a> or request the hardware clock register via <a href="/windows-hardware/drivers/audio/ksproperty-rtaudio-clockregister">KSPROPERTY_RTAUDIO_CLOCKREGISTER</a>.

## -struct-fields

### -field Property

A <a href="/windows-hardware/drivers/stream/ksproperty-structure">KSPROPERTY</a> structure that the client initializes appropriately prior to calling KSPROPERTY_RTAUDIO_POSITIONREGISTER or KSPROPERTY_RTAUDIO_CLOCKREGISTER.

### -field BaseAddress

Specifies the buffer base address.  Unless the client specifies a base address, this parameter is set to <b>NULL</b>.

## -remarks

The client uses the KSRTAUDIO_HWREGISTER_PROPERTY structure to request the hardware position register or the hardware clock register from the driver.  The driver returns a <a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksrtaudio_hwregister">KSRTAUDIO_HWREGISTER</a> structure containing information about the requested hardware register.

## -see-also

<a href="/windows-hardware/drivers/stream/ksproperty-structure">KSPROPERTY</a>



<a href="/windows-hardware/drivers/audio/ksproperty-rtaudio-clockregister">KSPROPERTY_RTAUDIO_CLOCKREGISTER</a>



<a href="/windows-hardware/drivers/audio/ksproperty-rtaudio-positionregister">KSPROPERTY_RTAUDIO_POSITIONREGISTER</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksrtaudio_hwregister">KSRTAUDIO_HWREGISTER</a>

