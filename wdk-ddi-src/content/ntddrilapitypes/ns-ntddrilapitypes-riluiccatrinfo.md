---
UID: NS:ntddrilapitypes.RILUICCATRINFO
title: RILUICCATRINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccatrinfo.htm
old-project: netvista
ms.assetid: 84ced2d3-43a9-42ef-b8fb-592dc960b01b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILUICCATRINFO structure [Network Drivers Starting with Windows Vista], ntddrilapitypes/RILUICCATRINFO, netvista.riluiccatrinfo, *LPRILUICCATRINFO, RILUICCATRINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	RILUICCATRINFO
product: Windows
targetos: Windows
req.typenames: "*LPRILUICCATRINFO, RILUICCATRINFO"
---

# RILUICCATRINFO structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILUICCATRINFO {
  DWORD     dwATRlength;
  BYTE [36] bATR;
} RILUICCATRINFO, RILUICCATRINFO;
````


## -struct-fields




### -field dwATRlength



### -field bATR


