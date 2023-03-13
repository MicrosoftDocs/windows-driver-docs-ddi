---
UID: NS:ksmedia.KSMUSICFORMAT
title: KSMUSICFORMAT (ksmedia.h)
description: The KSMUSICFORMAT structure is used to send and receive information about MIDI data that is input from and output to WDM audio devices.
tech.root: audio
ms.date: 03/10/2023
keywords: ["KSMUSICFORMAT structure"]
ms.keywords: "*PKSMUSICFORMAT, KSMUSICFORMAT, KSMUSICFORMAT structure [Audio Devices], PKSMUSICFORMAT, PKSMUSICFORMAT structure pointer [Audio Devices], aud-prop_04d08180-a7b6-4b88-aa9d-972e5dc237dd.xml, audio.ksmusicformat, ksmedia/KSMUSICFORMAT, ksmedia/PKSMUSICFORMAT"
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
req.typenames: KSMUSICFORMAT, *PKSMUSICFORMAT
f1_keywords:
 - PKSMUSICFORMAT
 - ksmedia/PKSMUSICFORMAT
 - KSMUSICFORMAT
 - ksmedia/KSMUSICFORMAT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - PKSMUSICFORMAT
 - KSMUSICFORMAT
---

## -description

The KSMUSICFORMAT structure is used to send and receive information about MIDI data that is input from and output to WDM audio devices.

## -struct-fields

### -field TimeDeltaMs

Indicates when this series of MIDI data bytes should be played. If this is the first KSMUSICFORMAT structure in the buffer, this field represents the delta (time change, in milliseconds) from the **PresentationTime** in the [KSSTREAM_HEADER](/windows-hardware/drivers/ddi/ks/ns-ks-ksstream_header) structure. Otherwise, the field represents the delta offset (in milliseconds) from the previous message (KSMUSICFORMAT structure). If this time is in the past, then the message is played immediately.

### -field ByteCount

Specifies the number of bytes of data that follow this structure. Because the subsequent structure or properties should be DWORD aligned and might allow for extra blanks or used bytes, **ByteCount** should be the actual number of bytes present and not include any padding separating the data structures.

## -remarks

This structure is used to send and receive IRPs containing information about MIDI input and output streams. The IRP itself contains in its **SystemBuffer** field a pointer to a KSSTREAM_HEADER structure, which serves as a header for a packet of data that is to be read from or written to a streaming driver pin. The KS stream header contains in its **Data** field a pointer to the buffer that contains the data. The data in that buffer consists of a sequence of messages, each of which is a KSMUSICFORMAT structure that is immediately followed by some number of bytes of data.

Time stamps in these IRPs always increase across successively issued IRPs. However, because each IRP in a sequence is fully serviced before servicing of the next IRP begins, time must also always increase across IRPs. This can lead to an anomalous situation, as described in the following example.

| Action | Description |
|---|---|
| IRP \#1 PresentationTime = 123 milliseconds |  |
| Message \#1 TimeDeltaMs: 0 | Will be played at 123 milliseconds. |
| Message \#2 TimeDeltaMs: 1 | Will be played at 124 milliseconds. |
| Message \#3 TimeDeltaMs: 7 | Will be played at 131 milliseconds. |
| IRP \#2 PresentationTime = 120 milliseconds |  |
| Message \#1 TimeDeltaMs: 5 | Supposed to be played at 125 milliseconds, but is actually played at 131 milliseconds. This IRP is not processed until the previous IRP at 131 milliseconds finishes. |
| Message \#2 TimeDeltaMs: 15 | Will be played at 140 milliseconds. |

## -see-also

[KSSTREAM_HEADER](/windows-hardware/drivers/ddi/ks/ns-ks-ksstream_header)
