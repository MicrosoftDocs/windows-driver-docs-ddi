---
UID: NS:rilapitypes.RILGPPREJECTCAUSE
title: RILGPPREJECTCAUSE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgpprejectcause_2.htm
old-project: netvista
ms.assetid: b182f937-3d0d-4558-967a-da2be3c73843
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: rilapitypes/RILGPPREJECTCAUSE, netvista.rilgpprejectcause_2, RILGPPREJECTCAUSE structure [Network Drivers Starting with Windows Vista], RILGPPREJECTCAUSE, *LPRILGPPREJECTCAUSE
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
-	RILGPPREJECTCAUSE
product: Windows
targetos: Windows
req.typenames: RILGPPREJECTCAUSE, *LPRILGPPREJECTCAUSE
req.product: Windows 10 or later.
---

# RILGPPREJECTCAUSE structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILGPPREJECTCAUSE {
  DWORD  dwCauseValue;
} RILGPPREJECTCAUSE, RILGPPREJECTCAUSE;
````


## -struct-fields




### -field dwCauseValue

