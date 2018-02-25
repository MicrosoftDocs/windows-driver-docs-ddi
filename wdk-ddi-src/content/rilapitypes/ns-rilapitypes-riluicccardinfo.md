---
UID: NS:rilapitypes.RILUICCCARDINFO
title: RILUICCCARDINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluicccardinfo_2.htm
old-project: netvista
ms.assetid: c49d538c-49c9-43ba-bc97-324706a5a5b9
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *LPRILUICCCARDINFO, ,, A, C, D, F, I, L, N, O, P, R, RILUICCCARDINFO, RILUICCCARDINFO structure [Network Drivers Starting with Windows Vista], U, netvista.riluicccardinfo_2, rilapitypes/RILUICCCARDINFO"
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
-	rilapitypes.h
apiname:
-	RILUICCCARDINFO
product: Windows
targetos: Windows
req.typenames: RILUICCCARDINFO, *LPRILUICCCARDINFO
req.product: Windows 10 or later.
---

# RILUICCCARDINFO structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILUICCCARDINFO {
  DWORD                  cbSize;
  DWORD                  dwParams;
  BOOL                   fIsVirtualCard;
  BYTE [MAXLENGTH_ICCID] IccId;
  DWORD                  dwNumApps;
  RILUICCAPPINFO [1]     AppInfo;
} RILUICCCARDINFO, RILUICCCARDINFO;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field fIsVirtualCard


### -field IccId


### -field dwNumApps


### -field AppInfo

