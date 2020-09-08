---
UID: NS:avc._AVCCONNECTINFO
title: _AVCCONNECTINFO (avc.h)
description: The AVCCONNECTINFO structure is used to initialize a subunit driver and establish pin connections.
old-location: stream\avcconnectinfo.htm
tech.root: stream
ms.assetid: ed6e01f0-fa30-4a42-8271-70afb2fde8c9
ms.date: 04/23/2018
keywords: ["AVCCONNECTINFO structure"]
ms.keywords: "*PAVCCONNECTINFO, AVCCONNECTINFO, AVCCONNECTINFO structure [Streaming Media Devices], PAVCCONNECTINFO, PAVCCONNECTINFO structure pointer [Streaming Media Devices], _AVCCONNECTINFO, avc/AVCCONNECTINFO, avc/PAVCCONNECTINFO, avcref_41c8705a-5735-4ab2-87f0-02b55b128c23.xml, stream.avcconnectinfo"
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
req.typenames: AVCCONNECTINFO, *PAVCCONNECTINFO
f1_keywords:
 - _AVCCONNECTINFO
 - avc/_AVCCONNECTINFO
 - PAVCCONNECTINFO
 - avc/PAVCCONNECTINFO
 - AVCCONNECTINFO
 - avc/AVCCONNECTINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - avc.h
api_name:
 - AVCCONNECTINFO
---

# _AVCCONNECTINFO structure


## -description

The AVCCONNECTINFO structure is used to initialize a subunit driver and establish pin connections.

## -struct-fields

### -field DeviceID

A GUID representing the unit as a whole. All subunits within the same unit share the same GUID. No two units share the same GUID.

### -field SubunitAddress

The encoded subunit type and subunit ID of the subunit.

### -field SubunitPlugNumber

The plug number (within the subunit) described by the AVCPRECONNECTINFO structure.

### -field DataFlow

The direction of data flow on this subunit plug. Destination plugs have KSPIN_DATAFLOW_IN; source plugs have KSPIN_DATAFLOW_OUT.

### -field hPlug

A plug handle obtained from <i>61883.sys</i> by the intersect handler according to the bit flags set in the associated AVCPRECONNECTINFO structure for this pin. If the proposed connection is between two subunits within the same unit, this value is <b>NULL</b>.

### -field UnitPlugNumber

The plug number (within the subunit) described by the AVCPRECONNECTINFO structure.

## -remarks

This structure is used only as member inside the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/avc/ns-avc-_avc_setconnect_info">AVC_SETCONNECT_INFO</a> structure. It is not used by itself.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avc-function-set-connectinfo">AVC_FUNCTION_SET_CONNECTINFO</a>

