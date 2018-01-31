---
UID: NS:nfcsedev._SECURE_ELEMENT_PROTO_ROUTING_INFO
title: "_SECURE_ELEMENT_PROTO_ROUTING_INFO"
author: windows-driver-content
description: SECURE_ELEMENT_PROTO_ROUTING_INFO is a member of SECURE_ELEMENT_ROUTING_TABLE_ENTRY.
old-location: nfpdrivers\_secure_element_proto_routing_info.htm
old-project: nfpdrivers
ms.assetid: E22C5985-13A8-4A55-A97B-DABD7E475BD3
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: P_SECURE_ELEMENT_PROTO_ROUTING_INFO structure pointer [Near-Field Proximity Drivers], SECURE_ELEMENT_PROTO_ROUTING_INFO, nfcsedev/_SECURE_ELEMENT_PROTO_ROUTING_INFO, SECURE_ELEMENT_PROTO_ROUTING_INFO structure [Near-Field Proximity Drivers], nfpdrivers._secure_element_proto_routing_info, nfcsedev/P_SECURE_ELEMENT_PROTO_ROUTING_INFO, PSECURE_ELEMENT_PROTO_ROUTING_INFO, *PSECURE_ELEMENT_PROTO_ROUTING_INFO, _SECURE_ELEMENT_PROTO_ROUTING_INFO, P_SECURE_ELEMENT_PROTO_ROUTING_INFO
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
-	SECURE_ELEMENT_PROTO_ROUTING_INFO
product: Windows
targetos: Windows
req.typenames: "*PSECURE_ELEMENT_PROTO_ROUTING_INFO, SECURE_ELEMENT_PROTO_ROUTING_INFO"
---

# _SECURE_ELEMENT_PROTO_ROUTING_INFO structure


## -description


SECURE_ELEMENT_PROTO_ROUTING_INFO
 is a member of <a href="..\nfcsedev\ns-nfcsedev-_secure_element_routing_table_entry.md">SECURE_ELEMENT_ROUTING_TABLE_ENTRY</a>. 


## -syntax


````
typedef struct _SECURE_ELEMENT_PROTO_ROUTING_INFO {
  GUID guidSecureElementId;
  BYTE eRfProtocolType;
} SECURE_ELEMENT_PROTO_ROUTING_INFO, *P_SECURE_ELEMENT_PROTO_ROUTING_INFO;
````


## -struct-fields




#### - guidSecureElementId

Secure element unique identifier returned by enumeration DDI.


#### - eRfProtocolType

NFC Forum RF protocol.

