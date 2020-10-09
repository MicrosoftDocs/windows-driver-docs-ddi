---
UID: NS:ksmedia.tagTRANSPORTSTATUS
title: tagTRANSPORTSTATUS (ksmedia.h)
description: The TRANSPORTSTATUS structure describes the current transport status.
old-location: stream\transportstatus.htm
tech.root: stream
ms.assetid: 2896fd39-5c33-4c79-8adb-f6862b7b4314
ms.date: 04/23/2018
keywords: ["tagTRANSPORTSTATUS structure"]
ms.keywords: "*PTRANSPORTSTATUS, PTRANSPORTSTATUS, PTRANSPORTSTATUS structure pointer [Streaming Media Devices], TRANSPORTSTATUS, TRANSPORTSTATUS structure [Streaming Media Devices], ksmedia/PTRANSPORTSTATUS, ksmedia/TRANSPORTSTATUS, stream.transportstatus, tagTRANSPORTSTATUS, vidcapstruct_12a98ac2-58b9-47ce-ae09-30c8feeec2f0.xml"
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
req.typenames: TRANSPORTSTATUS, *PTRANSPORTSTATUS
f1_keywords:
 - tagTRANSPORTSTATUS
 - ksmedia/tagTRANSPORTSTATUS
 - PTRANSPORTSTATUS
 - ksmedia/PTRANSPORTSTATUS
 - TRANSPORTSTATUS
 - ksmedia/TRANSPORTSTATUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - TRANSPORTSTATUS
---

# tagTRANSPORTSTATUS structure


## -description

The TRANSPORTSTATUS structure describes the current transport status.

## -struct-fields

### -field Mode

Specifies the ED_MODE_Xxx.

### -field LastError

Specifies the last error.

### -field RecordInhibit

Specifies if recording is inhibited. <b>TRUE</b> if recording is prevented, <b>FALSE</b> otherwise.

### -field ServoLock

Indicates the servo lock.

### -field MediaPresent

Specifies if media is present.

### -field MediaLength

Specifies the length of the media.

### -field MediaSize

Specifies the size of the media.

### -field MediaTrackCount

Indicates the media track count.

### -field MediaTrackLength

Specifies the media track length.

### -field MediaTrackSide

Indicates the media track size.

### -field MediaType

Indicates the type of media.

### -field LinkMode

Indicates linked mode. <b>TRUE</b> if linked, <b>FALSE</b> otherwise.

### -field NotifyOn

Specifies event notification. <b>TRUE</b> enables event notification, <b>FALSE</b> disables event notification.

## -remarks

Any ED_Xxx tokens are defined in <i>xprtdefs.h</i> in the Microsoft DirectX SDK.

