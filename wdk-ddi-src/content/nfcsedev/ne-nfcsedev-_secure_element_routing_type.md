---
UID: NE:nfcsedev._SECURE_ELEMENT_ROUTING_TYPE
title: "_SECURE_ELEMENT_ROUTING_TYPE"
author: windows-driver-content
description: SECURE_ELEMENT_ROUTING_TYPE is a member of SECURE_ELEMENT_ROUTING_TABLE_ENTRY.
old-location: nfpdrivers\_secure_element_routing_type.htm
old-project: nfpdrivers
ms.assetid: 1420D957-546E-4795-A545-B098C411CCA5
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: "_SECURE_ELEMENT_ROUTING_TYPE enumeration [Near-Field Proximity Drivers], RoutingTypeProtocol, RoutingTypeTech, _SECURE_ELEMENT_ROUTING_TYPE, SECURE_ELEMENT_ROUTING_TYPE, nfcsedev/RoutingTypeProtocol, RoutingTypeAid, nfcsedev/_SECURE_ELEMENT_ROUTING_TYPE, nfcsedev/RoutingTypeAid, nfcsedev/RoutingTypeTech, *PSECURE_ELEMENT_ROUTING_TYPE, nfpdrivers._secure_element_routing_type"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	SECURE_ELEMENT_ROUTING_TYPE
product: Windows
targetos: Windows
req.typenames: SECURE_ELEMENT_ROUTING_TYPE, *PSECURE_ELEMENT_ROUTING_TYPE
---

# _SECURE_ELEMENT_ROUTING_TYPE enumeration


## -description


SECURE_ELEMENT_ROUTING_TYPE
is a member of <a href="..\nfcsedev\ns-nfcsedev-_secure_element_routing_table_entry.md">SECURE_ELEMENT_ROUTING_TABLE_ENTRY</a>.


## -syntax


````
typedef enum _SECURE_ELEMENT_ROUTING_TYPE { 
  RoutingTypeTech      = 0,
  RoutingTypeProtocol  = 1,
  RoutingTypeAid       = 2
} SECURE_ELEMENT_ROUTING_TYPE;
````


## -enum-fields




### -field RoutingTypeTech

NFC Forum technology-based routing type.



### -field RoutingTypeProtocol

NFC Forum protocol-based routing type.



### -field RoutingTypeAid

NFC Forum AID-based routing type.


