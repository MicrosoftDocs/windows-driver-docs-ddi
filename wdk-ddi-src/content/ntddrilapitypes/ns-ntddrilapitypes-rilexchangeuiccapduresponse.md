---
UID: NS:ntddrilapitypes.RILEXCHANGEUICCAPDURESPONSE
title: RILEXCHANGEUICCAPDURESPONSE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilexchangeuiccapduresponse.htm
old-project: netvista
ms.assetid: 57418ab1-e341-41ad-a120-cc4f7e0b0227
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.rilexchangeuiccapduresponse, RILEXCHANGEUICCAPDURESPONSE structure [Network Drivers Starting with Windows Vista], *LPRILEXCHANGEUICCAPDURESPONSE, ntddrilapitypes/RILEXCHANGEUICCAPDURESPONSE, RILEXCHANGEUICCAPDURESPONSE
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
-	RILEXCHANGEUICCAPDURESPONSE
product: Windows
targetos: Windows
req.typenames: RILEXCHANGEUICCAPDURESPONSE, *LPRILEXCHANGEUICCAPDURESPONSE
---

# RILEXCHANGEUICCAPDURESPONSE structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILEXCHANGEUICCAPDURESPONSE {
  DWORD    cbSize;
  DWORD    dwParams;
  DWORD    dwResponseAPDULength;
  BYTE [1] bResponseAPDU;
} RILEXCHANGEUICCAPDURESPONSE, RILEXCHANGEUICCAPDURESPONSE;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwResponseAPDULength


### -field bResponseAPDU

