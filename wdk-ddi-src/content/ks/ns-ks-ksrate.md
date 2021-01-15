---
UID: NS:ks.__unnamed_struct_56
title: KSRATE (ks.h)
description: The query is passed a KSRATE structure appended to the property containing the rate request (known as a KSRATE_CAPABILITY structure), and is returned a KSRATE structure filled in with the capability given the rate request.
old-location: stream\ksrate.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KSRATE structure"]
ms.keywords: "*PKSRATE, KSRATE, KSRATE structure [Streaming Media Devices], PKSRATE, PKSRATE structure pointer [Streaming Media Devices], ks-struct_a47aa4cc-ff36-4a02-bd68-63c7ed450279.xml, ks/KSRATE, ks/PKSRATE, stream.ksrate"
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
req.typenames: KSRATE, *PKSRATE
f1_keywords:
 - PKSRATE
 - ks/PKSRATE
 - KSRATE
 - ks/KSRATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - PKSRATE
 - KSRATE
---

# KSRATE structure


## -description

The query is passed a KSRATE structure appended to the property containing the rate request (known as a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksrate_capability">KSRATE_CAPABILITY</a> structure), and is returned a KSRATE structure filled in with the capability given the rate request.

## -struct-fields

### -field PresentationStart

Specifies the start point for the rate in presentation time units.

### -field Duration

Specifies the duration of the rate in presentation time units.

### -field Interface

A structure of type <a href="/previous-versions/ff563537(v=vs.85)">KSPIN_INTERFACE</a> that specifies either the interface used in the connection this rate request is being sent to, or the interface of a related connection. This allows the time units to be interpreted by the pin.

### -field Rate

Specifies the rate in terms of 1/10th percentage points, where 1000 is the nominal 1.0 rate, 500 is 0.5 rate, and so on. Negative numbers indicate reverse rates.

### -field Flags

Possible flag values are listed in the following table.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
KSRATE_NOPRESENTATIONSTART

</td>
<td>
Specifies that there is no valid start time in this rate change request or query.

</td>
</tr>
<tr>
<td>
KSRATE_NOPRESENTATIONDURATION

</td>
<td>
Specifies that there is no valid duration in this rate change request or query.

</td>
</tr>
</table>

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksrate_capability">KSRATE_CAPABILITY</a>

