---
UID: NE:rilapitypes.RILINFOCLASS
title: RILINFOCLASS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilinfoclass_2.htm
old-project: netvista
ms.assetid: 19927cd1-8afa-4006-a882-d5222c690724
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILINFOCLASS, RILINFOCLASS
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
req.alt-api: RILINFOCLASS
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
req.typenames: RILINFOCLASS
req.product: Windows 10 or later.
---

# RILINFOCLASS enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef enum _RILINFOCLASS { 
  RIL_INFOCLASS_VOICE,
  RIL_INFOCLASS_DATA,
  RIL_INFOCLASS_FAX,
  RIL_INFOCLASS_SMS,
  RIL_INFOCLASS_DATACIRCUITSYNC,
  RIL_INFOCLASS_DATACIRCUITASYNC,
  RIL_INFOCLASS_PACKETACCESS,
  RIL_INFOCLASS_PADACCESS,
  RIL_INFOCLASS_ALL
} RILINFOCLASS;
````


## -enum-fields

### -field RIL_INFOCLASS_VOICE


### -field RIL_INFOCLASS_DATA


### -field RIL_INFOCLASS_FAX


### -field RIL_INFOCLASS_SMS


### -field RIL_INFOCLASS_DATACIRCUITSYNC


### -field RIL_INFOCLASS_DATACIRCUITASYNC


### -field RIL_INFOCLASS_PACKETACCESS


### -field RIL_INFOCLASS_PADACCESS


### -field RIL_INFOCLASS_ALL


## -remarks
