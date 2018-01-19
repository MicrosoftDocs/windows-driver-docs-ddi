---
UID: NE:rilapitypes.RILMESSAGETYPE
title: RILMESSAGETYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessagetype_2.htm
old-project: netvista
ms.assetid: 5f167bd5-a2b8-48a1-b403-e9ac68122ae4
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILMESSAGETYPE, RILMESSAGETYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILMESSAGETYPE
req.alt-loc: rilapitypes.h
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
req.product: Windows 10 or later.
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
