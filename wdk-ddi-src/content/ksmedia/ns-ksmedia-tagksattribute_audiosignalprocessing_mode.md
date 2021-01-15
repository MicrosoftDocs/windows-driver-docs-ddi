---
UID: NS:ksmedia.tagKSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE
title: tagKSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE (ksmedia.h)
description: The KSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE structure specifies an audio signal processing mode.
old-location: audio\ksattribute_audiosignalprocessing_mode.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["tagKSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE structure"]
ms.keywords: "*PKSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE, KSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE, KSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE structure [Audio Devices], PKSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE, PKSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE structure pointer [Audio Devices], audio.ksattribute_audiosignalprocessing_mode, ksmedia/KSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE, ksmedia/PKSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE, tagKSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE"
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
req.typenames: KSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE, *PKSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE
f1_keywords:
 - tagKSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE
 - ksmedia/tagKSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE
 - PKSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE
 - ksmedia/PKSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE
 - KSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE
 - ksmedia/KSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - tagKSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE
 - PKSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE
 - KSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE
---

# tagKSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE structure


## -description

The KSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE structure specifies an audio signal processing mode.

This structure is used to by mode aware drivers with  <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksdataformat">KSDATAFORMAT</a> which contain a  <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksmultiple_item">KSMULTIPLE_ITEM</a> of <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksattribute">KSATTRIBUTE</a> structures that reference a KSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE. The KSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE AttributeHeader.Attribute member is set to KSATTRIBUTEID_AUDIOSIGNALPROCESSING_MODE, and the KSATTRIBUTE_AUDIOSIGNALPROCESSING_MODE SignalProcessingMode member is set to AUDIO_SIGNALPROCESSINGMODE_DEFAULT or other processing modes that the driver supports. For more information, see <a href="/windows-hardware/drivers/stream/ks-data-formats-and-data-ranges">KS Data Formats and Data Ranges</a>.

## -struct-fields

### -field AttributeHeader

The AttributeHeader member specifies the attribute header using a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksattribute">KSATTRIBUTE</a> data type.

### -field SignalProcessingMode

The SignalProcessingMode member specifies the unique GUIDs of the SignalProcessingMode. For more information, see <a href="/windows-hardware/drivers/audio/audio-signal-processing-modes">Audio Signal Processing Modes</a>.

