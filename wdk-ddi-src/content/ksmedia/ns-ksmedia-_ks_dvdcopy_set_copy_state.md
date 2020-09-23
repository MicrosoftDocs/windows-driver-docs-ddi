---
UID: NS:ksmedia._KS_DVDCOPY_SET_COPY_STATE
title: _KS_DVDCOPY_SET_COPY_STATE (ksmedia.h)
description: The KS_DVDCOPY_SET_COPY_STATE structure is used to specify the copyright protection state of the DVD decoder stream.
old-location: stream\ks_dvdcopy_set_copy_state.htm
tech.root: stream
ms.assetid: e4f637b7-52ce-4ec8-8348-0b65a7f788ad
ms.date: 04/23/2018
keywords: ["KS_DVDCOPY_SET_COPY_STATE structure"]
ms.keywords: "*PKS_DVDCOPY_SET_COPY_STATE, KS_DVDCOPY_SET_COPY_STATE, KS_DVDCOPY_SET_COPY_STATE structure [Streaming Media Devices], PKS_DVDCOPY_SET_COPY_STATE, PKS_DVDCOPY_SET_COPY_STATE structure pointer [Streaming Media Devices], _KS_DVDCOPY_SET_COPY_STATE, dvdref_215efe26-9ca5-4f3b-836f-86a682cd88f8.xml, ksmedia/KS_DVDCOPY_SET_COPY_STATE, ksmedia/PKS_DVDCOPY_SET_COPY_STATE, stream.ks_dvdcopy_set_copy_state"
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
req.typenames: KS_DVDCOPY_SET_COPY_STATE, *PKS_DVDCOPY_SET_COPY_STATE
f1_keywords:
 - _KS_DVDCOPY_SET_COPY_STATE
 - ksmedia/_KS_DVDCOPY_SET_COPY_STATE
 - PKS_DVDCOPY_SET_COPY_STATE
 - ksmedia/PKS_DVDCOPY_SET_COPY_STATE
 - KS_DVDCOPY_SET_COPY_STATE
 - ksmedia/KS_DVDCOPY_SET_COPY_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KS_DVDCOPY_SET_COPY_STATE
---

# _KS_DVDCOPY_SET_COPY_STATE structure


## -description

The KS_DVDCOPY_SET_COPY_STATE structure is used to specify the copyright protection state of the DVD decoder stream.

## -struct-fields

### -field DVDCopyState

Indicates the progress of the copyright protection initialization, authentication and key negotiation sequence. This must be one of the values from the <a href="/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ks_dvdcopystate">KS_DVDCOPYSTATE</a> enumeration.

## -remarks

This structure is used by the <a href="/windows-hardware/drivers/stream/ksproperty-dvdcopy-set-copy-state">KSPROPERTY_DVDCOPY_SET_COPY_STATE</a> property.

For more information, see <a href="/windows-hardware/drivers/stream/dvd-copyright-protection">DVD Copyright Protection</a>, <a href="/windows-hardware/drivers/stream/multiple-data-streams-on-the-same-hardware">Multiple Data Streams on the same Hardware</a> and <a href="/windows-hardware/drivers/stream/synchronizing-key-exchange-with-data-flow">Synchronizing Key Exchange with Data Flow</a>.

## -see-also

<a href="/windows-hardware/drivers/stream/ksproperty-dvdcopy-set-copy-state">KSPROPERTY_DVDCOPY_SET_COPY_STATE</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ks_dvdcopystate">KS_DVDCOPYSTATE</a>