---
UID: NS:ks.KSRELATIVEEVENT
title: KSRELATIVEEVENT (ks.h)
description: The KSPROPERTY_CONNECTION_STARTAT property is passed a KSRELATIVEEVENT structure.
old-location: stream\ksrelativeevent.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KSRELATIVEEVENT structure"]
ms.keywords: KSRELATIVEEVENT, KSRELATIVEEVENT , KSRELATIVEEVENT structure [Streaming Media Devices], ks-struct_d79f6a15-6e44-4d81-b4f1-c113cbc2ee79.xml, ks/KSRELATIVEEVENT, stream.ksrelativeevent
req.header: ks.h
req.include-header: Ks.h
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
req.typenames: KSRELATIVEEVENT
f1_keywords:
 - KSRELATIVEEVENT
 - ks/KSRELATIVEEVENT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSRELATIVEEVENT
---

# KSRELATIVEEVENT structure


## -description

The <a href="/windows-hardware/drivers/stream/ksproperty-connection-startat">KSPROPERTY_CONNECTION_STARTAT</a> property is passed a KSRELATIVEEVENT structure.

## -struct-fields

### -field Size

Specifies the inclusive size of the structure, including any event specific data appended to the <b>EventData</b> member.

### -field Flags

Specifies what type of object is specified in the <b>ObjectHandle</b> and <b>ObjectPointer</b> union.

### -field ObjectHandle

Specifies the handle of the object supporting the event to be used if the <b>Flags</b> member contains the KSRELATIVEEVENT_FLAG_HANDLE flag.

### -field ObjectPointer

Specifies a pointer to the object supporting the event to be used if the Flags member contains the KSRELATIVEEVENT_FLAG_POINTER flag. This is valid only for kernel-mode clients.

### -field Reserved

Reserved and set to zero.

### -field Event

A <a href="/windows-hardware/drivers/stream/ksevent-structure">KSEVENT</a> structure that contains the event to be used.

### -field EventData

A <a href="/windows-hardware/drivers/ddi/ks/ns-ks-kseventdata">KSEVENTDATA</a> structure that specifies the header for the event-specific data. The header itself is not actually used except as a starting point to access the event-specific data, and must be initialized to zero.

