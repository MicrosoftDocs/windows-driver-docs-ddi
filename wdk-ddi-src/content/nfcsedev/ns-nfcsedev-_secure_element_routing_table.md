---
UID: NS:nfcsedev._SECURE_ELEMENT_ROUTING_TABLE
title: "_SECURE_ELEMENT_ROUTING_TABLE"
author: windows-driver-content
description: SECURE_ELEMENT_ROUTING_TABLE is an input parameter for IOCTL_NFCSE_SET_ROUTING_TABLE.
old-location: nfpdrivers\_secure_element_routing_table.htm
old-project: nfpdrivers
ms.assetid: AD5E6434-BBBF-44CB-8153-B8F4D4F75E94
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: "_SECURE_ELEMENT_ROUTING_TABLE, *PSECURE_ELEMENT_ROUTING_TABLE, PSECURE_ELEMENT_ROUTING_TABLE, P_SECURE_ELEMENT_ROUTING_TABLE structure pointer [Near-Field Proximity Drivers], nfpdrivers._secure_element_routing_table, P_SECURE_ELEMENT_ROUTING_TABLE, SECURE_ELEMENT_ROUTING_TABLE, SECURE_ELEMENT_ROUTING_TABLE structure [Near-Field Proximity Drivers], nfcsedev/P_SECURE_ELEMENT_ROUTING_TABLE, nfcsedev/_SECURE_ELEMENT_ROUTING_TABLE"
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
-	SECURE_ELEMENT_ROUTING_TABLE
product: Windows
targetos: Windows
req.typenames: "*PSECURE_ELEMENT_ROUTING_TABLE, SECURE_ELEMENT_ROUTING_TABLE"
---

# _SECURE_ELEMENT_ROUTING_TABLE structure


## -description


SECURE_ELEMENT_ROUTING_TABLE is an input parameter for <a href="..\nfcsedev\ni-nfcsedev-ioctl_nfcse_set_routing_table.md">IOCTL_NFCSE_SET_ROUTING_TABLE</a>.


## -syntax


````
typedef struct _SECURE_ELEMENT_ROUTING_TABLE {
  DWORD                                                                NumberOfEntries;
  _Field_size_(NumberOfEntries)
    SECURE_ELEMENT_ROUTING_TABLE_ENTRY TableEntries[ANYSIZE_ARRAY];
} SECURE_ELEMENT_ROUTING_TABLE, *P_SECURE_ELEMENT_ROUTING_TABLE;
````


## -struct-fields




### -field NumberOfEntries

Number of routing table entries.


### -field TableEntries

 




#### - TableEntries[ANYSIZE_ARRAY]

Listen mode routing table.

