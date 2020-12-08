---
UID: NE:bthddi._SCO_LINK_TYPE
title: _SCO_LINK_TYPE (bthddi.h)
description: The SCO_LINK_TYPE enumeration type describes the type of link used by the SCO connection when a ScoIndicationRemoteConnect indication event is processed.
old-location: bltooth\sco_link_type.htm
tech.root: bltooth
ms.date: 04/27/2018
keywords: ["SCO_LINK_TYPE enumeration"]
ms.keywords: "*PSCO_LINK_TYPE, PSCO_LINK_TYPE, PSCO_LINK_TYPE enumeration pointer [Bluetooth Devices], SCO_LINK_TYPE, SCO_LINK_TYPE enumeration [Bluetooth Devices], ScoLinkType, _SCO_LINK_TYPE, bltooth.sco_link_type, bth_enums_c5b9357f-7046-4115-a8a7-add459e59f27.xml, bthddi/PSCO_LINK_TYPE, bthddi/SCO_LINK_TYPE, bthddi/ScoLinkType, bthddi/eScoLinkType, eScoLinkType"
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.typenames: SCO_LINK_TYPE, *PSCO_LINK_TYPE
f1_keywords:
 - _SCO_LINK_TYPE
 - bthddi/_SCO_LINK_TYPE
 - PSCO_LINK_TYPE
 - bthddi/PSCO_LINK_TYPE
 - SCO_LINK_TYPE
 - bthddi/SCO_LINK_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - bthddi.h
api_name:
 - SCO_LINK_TYPE
---

# _SCO_LINK_TYPE enumeration


## -description

The SCO_LINK_TYPE enumeration type describes the type of link used by the SCO connection when a 
  <b>ScoIndicationRemoteConnect</b> indication event is processed.

## -enum-fields

### -field ScoLinkType

This value indicates that the link used by the connection is a SCO link.

### -field eScoLinkType

This value indicates that the link used by the connection is an eSCO link.

## -remarks

The 
    <a href="/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_sco_indication_parameters">SCO_INDICATION_PARAMETERS</a> structure
    uses this enumeration.

## -see-also

<a href="/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_sco_indication_parameters">SCO_INDICATION_PARAMETERS</a>
