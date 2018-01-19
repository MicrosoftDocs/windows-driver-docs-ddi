---
UID: NS:rilapitypes.RILUICCATRINFO
title: RILUICCATRINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccatrinfo_2.htm
old-project: netvista
ms.assetid: d7deda33-b68a-4413-a7fc-2988e97906e1
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILUICCATRINFO, RILUICCATRINFO, *LPRILUICCATRINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILUICCATRINFO
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
req.typenames: RILUICCATRINFO, *LPRILUICCATRINFO
req.product: Windows 10 or later.
---

# RILUICCATRINFO structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILUICCATRINFO {
  DWORD                dwATRlength;
  BYTE [MAXLENGTH_ATR] bATR;
} RILUICCATRINFO, RILUICCATRINFO;
````


## -struct-fields

### -field dwATRlength


### -field bATR


## -remarks
