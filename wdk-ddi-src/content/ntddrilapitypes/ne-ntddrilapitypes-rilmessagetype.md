---
UID: NE:ntddrilapitypes.RILMESSAGETYPE
title: RILMESSAGETYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessagetype.htm
old-project: netvista
ms.assetid: 02960e7c-f1b2-4c28-9f9b-f180df3d9563
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilmessagetype, RILMESSAGETYPE enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_MSGTYPE_OUT_CDMASUBMIT, ntddrilapitypes/RIL_MSGTYPE_IN_CDMADELIVER, ntddrilapitypes/RIL_MSGTYPE_IN_IS637STATUS, RIL_MSGTYPE_OUT_SUBMIT, RIL_MSGTYPE_IN_CDMADELIVER, RIL_MSGTYPE_BC_GENERAL, RIL_MSGTYPE_IN_STATUS, ntddrilapitypes/RIL_MSGTYPE_BC_GENERAL, RIL_MSGTYPE_IN_IS637STATUS, ntddrilapitypes/RIL_MSGTYPE_IN_STATUS, ntddrilapitypes/RILMESSAGETYPE, ntddrilapitypes/RIL_MSGTYPE_OUT_SUBMIT, RIL_MSGTYPE_OUT_CDMASUBMIT, RILMESSAGETYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
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
-	ntddrilapitypes.h
apiname:
-	RILMESSAGETYPE
product: Windows
targetos: Windows
req.typenames: RILMESSAGETYPE
---

# RILMESSAGETYPE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILMESSAGETYPE { 
  RIL_MSGTYPE_IN_STATUS,
  RIL_MSGTYPE_IN_IS637STATUS,
  RIL_MSGTYPE_IN_CDMADELIVER,
  RIL_MSGTYPE_OUT_SUBMIT,
  RIL_MSGTYPE_OUT_CDMASUBMIT,
  RIL_MSGTYPE_BC_GENERAL
} RILMESSAGETYPE;
````


## -enum-fields




### -field RIL_MSGTYPE_IN_DELIVER



#### - RIL_MSGTYPE_IN_STATUS



#### - RIL_MSGTYPE_IN_IS637STATUS



#### - RIL_MSGTYPE_IN_CDMADELIVER



#### - RIL_MSGTYPE_OUT_SUBMIT



#### - RIL_MSGTYPE_OUT_CDMASUBMIT



#### - RIL_MSGTYPE_BC_GENERAL


