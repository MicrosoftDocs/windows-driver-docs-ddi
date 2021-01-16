---
UID: NS:61883._OPCR
title: _OPCR (61883.h)
description: The OPCR structure contains initialization values for an output plug.
old-location: ieee\opcr.htm
tech.root: IEEE
ms.date: 02/15/2018
keywords: ["OPCR structure"]
ms.keywords: "*POPCR, 61883/OPCR, 61883/POPCR, 61883_structures_271facde-3b80-421f-a3d2-1f0e9b8e1782.xml, IEEE.opcr, OPCR, OPCR structure [Buses], POPCR, POPCR structure pointer [Buses], _OPCR"
req.header: 61883.h
req.include-header: 61883.h
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
req.typenames: OPCR, *POPCR
f1_keywords:
 - _OPCR
 - 61883/_OPCR
 - POPCR
 - 61883/POPCR
 - OPCR
 - 61883/OPCR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 61883.h
api_name:
 - _OPCR
 - POPCR
 - OPCR
---

# _OPCR structure


## -description

The OPCR structure contains initialization values for an output plug.

## -struct-fields

### -field Payload

Specifies the connection speed.

### -field OverheadID

Specifies, for an unconnected output plug, the upper bounds for the bandwidth that the output plug needs for the transmission of an isochronous packet.

### -field DataRate

Indicates the bit rate that the output plug uses to transmit an isochronous packet.

### -field Channel

Indicates the channel number that the output plug shall use to transmit the isochronous data flow, for a suspended output plug. For an active output plug it indicates the actual channel number that the output plug uses to transmit the isochronous data flow. For an unconnected output plug it has no meaning.

### -field Reserved

Reserved.

### -field PPCCounter

Indicates the number of point-to-point connections to the output plug.

### -field BCCCounter

Indicates, when one, that there is a broadcast-out connection to the output plug. When zero it indicates that there is no connection.

### -field OnLine

Indicates, when one, that the corresponding output plug is on-line. When zero it indicates that the output plug is off-line.

## -see-also

<a href="/windows-hardware/drivers/ddi/61883/ns-61883-_av_pcr">AV_PCR</a>

