---
UID: NS:nfcsedev._SECURE_ELEMENT_ROUTING_TABLE_ENTRY
title: "_SECURE_ELEMENT_ROUTING_TABLE_ENTRY"
author: windows-driver-content
description: SECURE_ELEMENT_ROUTING_TABLE_ENTRY is a member of SECURE_ELEMENT_ROUTING_TABLE.
old-location: nfpdrivers\_secure_element_routing_table_entry.htm
old-project: nfpdrivers
ms.assetid: 199FEA6A-A57F-4B13-832A-65DB7729455F
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: P_SECURE_ELEMENT_ROUTING_TABLE_ENTRY structure pointer [Near-Field Proximity Drivers], _SECURE_ELEMENT_ROUTING_TABLE_ENTRY, SECURE_ELEMENT_ROUTING_TABLE_ENTRY, P_SECURE_ELEMENT_ROUTING_TABLE_ENTRY, nfcsedev/P_SECURE_ELEMENT_ROUTING_TABLE_ENTRY, *PSECURE_ELEMENT_ROUTING_TABLE_ENTRY, nfpdrivers._secure_element_routing_table_entry, nfcsedev/_SECURE_ELEMENT_ROUTING_TABLE_ENTRY, SECURE_ELEMENT_ROUTING_TABLE_ENTRY structure [Near-Field Proximity Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	nfcsedev.h
apiname:
-	SECURE_ELEMENT_ROUTING_TABLE_ENTRY
product: Windows
targetos: Windows
req.typenames: SECURE_ELEMENT_ROUTING_TABLE_ENTRY, *PSECURE_ELEMENT_ROUTING_TABLE_ENTRY
---

# _SECURE_ELEMENT_ROUTING_TABLE_ENTRY structure


## -description


SECURE_ELEMENT_ROUTING_TABLE_ENTRY is a member of <a href="..\nfcsedev\ns-nfcsedev-_secure_element_routing_table.md">SECURE_ELEMENT_ROUTING_TABLE</a>.


## -syntax


````
typedef struct _SECURE_ELEMENT_ROUTING_TABLE_ENTRY {
  SECURE_ELEMENT_ROUTING_TYPE eRoutingType;
  union {
    SECURE_ELEMENT_TECH_ROUTING_INFO  TechRoutingInfo;
    SECURE_ELEMENT_PROTO_ROUTING_INFO ProtoRoutingInfo;
    SECURE_ELEMENT_AID_ROUTING_INFO   AidRoutingInfo;
  };
} SECURE_ELEMENT_ROUTING_TABLE_ENTRY, *P_SECURE_ELEMENT_ROUTING_TABLE_ENTRY;
````


## -struct-fields




### -field eRoutingType

NFC Forum listen mode routing table entry type.



#### - TechRoutingInfo

RF technology routing table entry information.


#### - ProtoRoutingInfo

RF protocol routing table entry information.


#### - AidRoutingInfo

AID routing table control information.


