---
UID: NS:nfcsedev._SECURE_ELEMENT_AID_ROUTING_INFO
title: _SECURE_ELEMENT_AID_ROUTING_INFO (nfcsedev.h)
description: SECURE_ELEMENT_AID_ROUTING_INFO is a member of SECURE_ELEMENT_ROUTING_TABLE_ENTRY.
old-location: nfpdrivers\_secure_element_aid_routing_info.htm
tech.root: nfpdrivers
ms.assetid: 3F9831D1-68A9-4FDB-93C6-6983E6BFE945
ms.date: 02/15/2018
keywords: ["SECURE_ELEMENT_AID_ROUTING_INFO structure"]
ms.keywords: "*PSECURE_ELEMENT_AID_ROUTING_INFO, P_SECURE_ELEMENT_AID_ROUTING_INFO, P_SECURE_ELEMENT_AID_ROUTING_INFO structure pointer [Near-Field Proximity Drivers], SECURE_ELEMENT_AID_ROUTING_INFO, SECURE_ELEMENT_AID_ROUTING_INFO structure [Near-Field Proximity Drivers], _SECURE_ELEMENT_AID_ROUTING_INFO, nfcsedev/P_SECURE_ELEMENT_AID_ROUTING_INFO, nfcsedev/_SECURE_ELEMENT_AID_ROUTING_INFO, nfpdrivers._secure_element_aid_routing_info"
req.header: nfcsedev.h
req.include-header: 
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
req.typenames: SECURE_ELEMENT_AID_ROUTING_INFO, *PSECURE_ELEMENT_AID_ROUTING_INFO
f1_keywords:
 - _SECURE_ELEMENT_AID_ROUTING_INFO
 - nfcsedev/_SECURE_ELEMENT_AID_ROUTING_INFO
 - PSECURE_ELEMENT_AID_ROUTING_INFO
 - nfcsedev/PSECURE_ELEMENT_AID_ROUTING_INFO
 - SECURE_ELEMENT_AID_ROUTING_INFO
 - nfcsedev/SECURE_ELEMENT_AID_ROUTING_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - nfcsedev.h
api_name:
 - SECURE_ELEMENT_AID_ROUTING_INFO
---

# _SECURE_ELEMENT_AID_ROUTING_INFO structure


## -description

SECURE_ELEMENT_AID_ROUTING_INFO is a member of <a href="/windows-hardware/drivers/ddi/nfcsedev/ns-nfcsedev-_secure_element_routing_table_entry">SECURE_ELEMENT_ROUTING_TABLE_ENTRY</a>.

## -struct-fields

### -field guidSecureElementId

Secure element unique identifier returned by enumeration DDI.

### -field cbAid

Length of applet ID buffer.

### -field pbAid

 




#### - pbAid[16]

Buffer holding ISO 7816 AID.