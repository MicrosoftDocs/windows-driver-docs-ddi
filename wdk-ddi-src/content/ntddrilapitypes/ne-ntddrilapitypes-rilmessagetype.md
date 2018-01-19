---
UID: NE:ntddrilapitypes.RILMESSAGETYPE
title: RILMESSAGETYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessagetype.htm
old-project: netvista
ms.assetid: 02960e7c-f1b2-4c28-9f9b-f180df3d9563
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILMESSAGETYPE, RILMESSAGETYPE
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
req.alt-api: RILMESSAGETYPE
req.alt-loc: ntddrilapitypes.h
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

### -field RIL_MSGTYPE_IN_STATUS


### -field RIL_MSGTYPE_IN_IS637STATUS


### -field RIL_MSGTYPE_IN_CDMADELIVER


### -field RIL_MSGTYPE_OUT_SUBMIT


### -field RIL_MSGTYPE_OUT_CDMASUBMIT


### -field RIL_MSGTYPE_BC_GENERAL


## -remarks
