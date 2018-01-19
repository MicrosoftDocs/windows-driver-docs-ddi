---
UID: NE:rilapitypes.RILMESSAGEFLAGS
title: RILMESSAGEFLAGS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessageflags_2.htm
old-project: netvista
ms.assetid: 49f8bd1b-5c8a-47d3-a5d5-817216562559
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILMESSAGEFLAGS, RILMESSAGEFLAGS
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
req.alt-api: RILMESSAGEFLAGS
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
req.typenames: RILMESSAGEFLAGS
req.product: Windows 10 or later.
---

# RILMESSAGEFLAGS enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef enum _RILMESSAGEFLAGS { 
  RIL_MSGFLAG_MORETOSEND,
  RIL_MSGFLAG_REPLYPATH,
  RIL_MSGFLAG_HEADER,
  RIL_MSGFLAG_REJECTDUPS,
  RIL_MSGFLAG_STATUSREPORTRETURNED,
  RIL_MSGFLAG_STATUSREPORTREQUESTED,
  RIL_MSGFLAG_CAUSEDBYCOMMAND,
  RIL_MSGFLAG_ALL
} RILMESSAGEFLAGS;
````


## -enum-fields

### -field RIL_MSGFLAG_MORETOSEND


### -field RIL_MSGFLAG_REPLYPATH


### -field RIL_MSGFLAG_HEADER


### -field RIL_MSGFLAG_REJECTDUPS


### -field RIL_MSGFLAG_STATUSREPORTRETURNED


### -field RIL_MSGFLAG_STATUSREPORTREQUESTED


### -field RIL_MSGFLAG_CAUSEDBYCOMMAND


### -field RIL_MSGFLAG_ALL


## -remarks
