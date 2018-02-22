---
UID: NS:ntddrilapitypes.RILEXCHANGEUICCAPDUPARAMS
title: RILEXCHANGEUICCAPDUPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilexchangeuiccapduparams.htm
old-project: netvista
ms.assetid: be77f9e2-acf7-4b59-9a46-abda7c43817b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntddrilapitypes/RILEXCHANGEUICCAPDUPARAMS, RILEXCHANGEUICCAPDUPARAMS structure [Network Drivers Starting with Windows Vista], *LPRILEXCHANGEUICCAPDUPARAMS, RILEXCHANGEUICCAPDUPARAMS, netvista.rilexchangeuiccapduparams
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
-	RILEXCHANGEUICCAPDUPARAMS
product: Windows
targetos: Windows
req.typenames: "*LPRILEXCHANGEUICCAPDUPARAMS, RILEXCHANGEUICCAPDUPARAMS"
---

# RILEXCHANGEUICCAPDUPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILEXCHANGEUICCAPDUPARAMS {
  DWORD    dwSlotIndex;
  DWORD    dwChannelId;
  DWORD    dwAPDULength;
  BYTE [1] bAPDU;
} RILEXCHANGEUICCAPDUPARAMS, RILEXCHANGEUICCAPDUPARAMS;
````


## -struct-fields




### -field dwSlotIndex


### -field dwChannelId


### -field dwAPDULength


### -field bAPDU

