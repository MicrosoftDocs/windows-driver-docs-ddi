---
UID: NE:iscsidef.PISCSI_AUTH_TYPES
title: "*PISCSI_AUTH_TYPES"
author: windows-driver-content
description: The ISCSI_AUTH_TYPES enumeration indicates the type of authentication method that is used to establish a logon connection.
old-location: storage\iscsi_auth_types.htm
old-project: storage
ms.assetid: b1d38829-53bc-42a5-acaf-c1ad89b8b563
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: "*PISCSI_AUTH_TYPES, iscsidef/PISCSI_AUTH_TYPES, PISCSI_AUTH_TYPES, PISCSI_AUTH_TYPES enumeration pointer [Storage Devices], storage.iscsi_auth_types, iscsidef/ISCSI_NO_AUTH_TYPE, ISCSI_MUTUAL_CHAP_AUTH_TYPE, iscsidef/ISCSI_MUTUAL_CHAP_AUTH_TYPE, iscsidef/ISCSI_AUTH_TYPES, ISCSI_AUTH_TYPES enumeration [Storage Devices], ISCSI_CHAP_AUTH_TYPE, ISCSI_AUTH_TYPES, structs-iSCSI_a55ac905-6962-416f-a197-778a24eae524.xml, iscsidef/ISCSI_CHAP_AUTH_TYPE, ISCSI_NO_AUTH_TYPE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: iscsidef.h
req.include-header: Iscsidef.h
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
-	iscsidef.h
apiname:
-	ISCSI_AUTH_TYPES
product: Windows
targetos: Windows
req.typenames: "*PISCSI_AUTH_TYPES, ISCSI_AUTH_TYPES"
---

# *PISCSI_AUTH_TYPES enumeration


## -description


The ISCSI_AUTH_TYPES enumeration indicates the type of authentication method that is used to establish a logon connection. 


## -syntax


````
typedef enum  { 
  ISCSI_NO_AUTH_TYPE           = 0,
  ISCSI_CHAP_AUTH_TYPE         = 1,
  ISCSI_MUTUAL_CHAP_AUTH_TYPE  = 2
} ISCSI_AUTH_TYPES, *PISCSI_AUTH_TYPES;
````


## -enum-fields




### -field ISCSI_NO_AUTH_TYPE

No authentication type was specified. 


### -field ISCSI_CHAP_AUTH_TYPE

Challenge handshake authentication protocol (CHAP).


### -field ISCSI_MUTUAL_CHAP_AUTH_TYPE

Mutual (2-way) CHAP authentication.

