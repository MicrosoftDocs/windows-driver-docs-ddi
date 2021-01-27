---
UID: NS:ksmedia.__unnamed_struct_4
title: KSDATAFORMAT_WAVEFORMATEXTENSIBLE (ksmedia.h)
description: The KSDATAFORMAT_WAVEFORMATEXTENSIBLE structure is a convenient wrapper structure for the case in which the WaveFormatExt does not contain extra data.
tech.root: audio
ms.date: 01/15/2021
ms.topic: language-reference
keywords: ["KSDATAFORMAT_WAVEFORMATEXTENSIBLE structure"]
ms.keywords: "*PKSDATAFORMAT_WAVEFORMATEXENSIBLE, KSDATAFORMAT_WAVEFORMATEXENSIBLE, KSDATAFORMAT_WAVEFORMATEXENSIBLE structure [Audio Devices], PKSDATAFORMAT_WAVEFORMATEXENSIBLE, PKSDATAFORMAT_WAVEFORMATEXENSIBLE structure pointer [Audio Devices], audio.ksdataformat_waveformatextensible, ksmedia/KSDATAFORMAT_WAVEFORMATEXENSIBLE, ksmedia/PKSDATAFORMAT_WAVEFORMATEXENSIBLE"
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.construct-type: structure
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
req.typenames: KSDATAFORMAT_WAVEFORMATEXTENSIBLE, *PKSDATAFORMAT_WAVEFORMATEXTENSIBLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - PKSDATAFORMAT_WAVEFORMATEXTENSIBLE
 - KSDATAFORMAT_WAVEFORMATEXTENSIBLE
f1_keywords:
 - PKSDATAFORMAT_WAVEFORMATEXTENSIBLE
 - ksmedia/PKSDATAFORMAT_WAVEFORMATEXTENSIBLE
 - KSDATAFORMAT_WAVEFORMATEXTENSIBLE
 - ksmedia/KSDATAFORMAT_WAVEFORMATEXTENSIBLE
---

# KSDATAFORMAT_WAVEFORMATEXTENSIBLE structure


## -description

The KSDATAFORMAT_WAVEFORMATEXTENSIBLE structure is a convenient wrapper structure for the case in which the WaveFormatExt is known not to contain extra data.

## -struct-fields

### -field DataFormat

Specifies the general features of the stream's data format. This member is a structure of type <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksdataformat">KSDATAFORMAT</a>.

### -field WaveFormatExt

Describes the wave-specific details of the audio stream's data format. This member contains an initialized <a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-waveformatextensible">WAVEFORMATEXTENSIBLE</a> structure.

## -remarks

For information refer to the <a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksdataformat_waveformatex">KSDATAFORMAT_WAVEFORMATEX</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiport-datarangeintersection">IMiniport::DataRangeIntersection</a>

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksdataformat">KSDATAFORMAT</a>

<a href="/windows/win32/api/mmreg/ns-mmreg-waveformatex">WAVEFORMATEX</a>

<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-waveformatextensible">WAVEFORMATEXTENSIBLE</a>

<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksdataformat_waveformatex">KSDATAFORMAT_WAVEFORMATEX</a>
