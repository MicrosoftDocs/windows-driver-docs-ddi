---
UID: NE:ksmedia.__unnamed_enum_51
title: KS_DVDCOPYSTATE (ksmedia.h)
description: The KS_DVDCOPYSTATE enumeration describes the progress of the DVD copyright protection initialization, authentication and key negotiation sequence.
old-location: stream\ks_dvdcopystate.htm
tech.root: stream
ms.assetid: 4072eaf1-d4cc-4255-90c1-177d6d58bb0a
ms.date: 04/30/2019
keywords: ["KS_DVDCOPYSTATE enumeration"]
ms.keywords: KS_DVDCOPYSTATE, KS_DVDCOPYSTATE enumeration [Streaming Media Devices], KS_DVDCOPYSTATE_AUTHENTICATION_NOT_REQUIRED, KS_DVDCOPYSTATE_AUTHENTICATION_REQUIRED, KS_DVDCOPYSTATE_DONE, KS_DVDCOPYSTATE_INITIALIZE, KS_DVDCOPYSTATE_INITIALIZE_TITLE, dvdref_f91c9ef4-f31c-4065-8017-26ef6ef76708.xml, ksmedia/KS_DVDCOPYSTATE, ksmedia/KS_DVDCOPYSTATE_AUTHENTICATION_NOT_REQUIRED, ksmedia/KS_DVDCOPYSTATE_AUTHENTICATION_REQUIRED, ksmedia/KS_DVDCOPYSTATE_DONE, ksmedia/KS_DVDCOPYSTATE_INITIALIZE, ksmedia/KS_DVDCOPYSTATE_INITIALIZE_TITLE, stream.ks_dvdcopystate
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
req.typenames: KS_DVDCOPYSTATE
f1_keywords:
 - KS_DVDCOPYSTATE
 - ksmedia/KS_DVDCOPYSTATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KS_DVDCOPYSTATE
---

# KS_DVDCOPYSTATE enumeration


## -description

The KS_DVDCOPYSTATE enumeration describes the progress of the DVD copyright protection initialization, authentication and key negotiation sequence.

## -enum-fields

### -field KS_DVDCOPYSTATE_INITIALIZE

Indicates that the full copyright protection sequence is starting.

### -field KS_DVDCOPYSTATE_INITIALIZE_TITLE

Indicates that a title key copyright protection sequence is starting.

### -field KS_DVDCOPYSTATE_AUTHENTICATION_NOT_REQUIRED

Indicates that no authentication is required.

### -field KS_DVDCOPYSTATE_AUTHENTICATION_REQUIRED

Indicates that authentication is required.

### -field KS_DVDCOPYSTATE_DONE

Indicates that the copyright protection sequence is complete.

## -see-also

<a href="/windows-hardware/drivers/stream/ksproperty-dvdcopy-set-copy-state">KSPROPERTY_DVDCOPY_SET_COPY_STATE</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-_ks_dvdcopy_set_copy_state">KS_DVDCOPY_SET_COPY_STATE</a>