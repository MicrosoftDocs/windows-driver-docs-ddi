---
UID: NE:avc._KSPIN_FLAG_AVC
title: _KSPIN_FLAG_AVC (avc.h)
description: The KSPIN_FLAG_AVC enumeration type is used for connection management and in the AVC_FUNCTION_GET_CONNECTINFO function code.
old-location: stream\kspin_flag_avc.htm
tech.root: stream
ms.assetid: 45a85718-8997-4c54-b283-e26247866735
ms.date: 04/23/2018
keywords: ["KSPIN_FLAG_AVC enumeration"]
ms.keywords: KSPIN_FLAG_AVC, KSPIN_FLAG_AVC enumeration [Streaming Media Devices], KSPIN_FLAG_AVCMASK, KSPIN_FLAG_AVC_CONNECTED, KSPIN_FLAG_AVC_FIXEDPCR, KSPIN_FLAG_AVC_PCRONLY, KSPIN_FLAG_AVC_PERMANENT, _KSPIN_FLAG_AVC, avc/KSPIN_FLAG_AVC, avc/KSPIN_FLAG_AVCMASK, avc/KSPIN_FLAG_AVC_CONNECTED, avc/KSPIN_FLAG_AVC_FIXEDPCR, avc/KSPIN_FLAG_AVC_PCRONLY, avc/KSPIN_FLAG_AVC_PERMANENT, avcref_9fab0898-b113-4d2f-ae4a-8cc6b01217d9.xml, stream.kspin_flag_avc
req.header: avc.h
req.include-header: Avc.h
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
req.typenames: KSPIN_FLAG_AVC
f1_keywords:
 - _KSPIN_FLAG_AVC
 - avc/_KSPIN_FLAG_AVC
 - KSPIN_FLAG_AVC
 - avc/KSPIN_FLAG_AVC
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - avc.h
api_name:
 - KSPIN_FLAG_AVC
---

# _KSPIN_FLAG_AVC enumeration


## -description

The KSPIN_FLAG_AVC enumeration type is used for connection management and in the <b>AVC_FUNCTION_GET_CONNECTINFO</b> function code.

## -enum-fields

### -field KSPIN_FLAG_AVCMASK

The mask to isolate the AV/C defined bit flags

### -field KSPIN_FLAG_AVC_PERMANENT

Part of the AV/C Connect Status bitmask. Represents a permanent connection between two subunits within the same unit.

### -field KSPIN_FLAG_AVC_CONNECTED

Part of the AV/C Connect Status bitmask. Represents a connection that is currently active, but not necessarily permanent.

### -field KSPIN_FLAG_AVC_PCRONLY

No subunit plug control. Only unit input and output plugs are available, and this AVCPRECONNECTINFO structure represents one of them.

### -field KSPIN_FLAG_AVC_FIXEDPCR

Represents a permanent connection between a subunit plug and a unit (serial bus) plug. Specifying this flag implies KSPIN_FLAG_AVC_PERMANENT, although that bit is not set if this one is set.

## -remarks

These bit flags are used by the intersect handler to determine plug compatibility, as well as to indicate whether the intersect handler is responsible for obtaining a plug handle from <i>61883.sys</i>.

## -see-also

<a href="/windows-hardware/drivers/ddi/avc/nc-avc-pfnavcintersecthandler">AV/C Intersect Handler</a>



<a href="/windows-hardware/drivers/stream/avc-function-get-connectinfo">AVC_FUNCTION_GET_CONNECTINFO</a>