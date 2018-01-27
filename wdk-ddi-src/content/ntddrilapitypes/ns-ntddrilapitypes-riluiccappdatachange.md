---
UID: NS:ntddrilapitypes.RILUICCAPPDATACHANGE
title: RILUICCAPPDATACHANGE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccappdatachange.htm
old-project: netvista
ms.assetid: a551f469-96f4-42cf-826d-3557cc13ce29
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILUICCAPPDATACHANGE, netvista.riluiccappdatachange, RILUICCAPPDATACHANGE structure [Network Drivers Starting with Windows Vista], *LPRILUICCAPPDATACHANGE, ntddrilapitypes/RILUICCAPPDATACHANGE
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
-	RILUICCAPPDATACHANGE
product: Windows
targetos: Windows
req.typenames: RILUICCAPPDATACHANGE, *LPRILUICCAPPDATACHANGE
---

# RILUICCAPPDATACHANGE structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILUICCAPPDATACHANGE {
  DWORD                     cbSize;
  HUICCAPP                  hUiccApp;
  RILUICCAPPDATACHANGEENUM  dwDataChange;
} RILUICCAPPDATACHANGE, RILUICCAPPDATACHANGE;
````


## -struct-fields




### -field cbSize



### -field hUiccApp



### -field dwDataChange


