---
UID: NS:ntddrilapitypes.RILIMSHANDOVERATTEMPT
title: RILIMSHANDOVERATTEMPT
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimshandoverattempt.htm
old-project: netvista
ms.assetid: 22491e3c-fa23-473d-b3e6-92c776b81204
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RILIMSHANDOVERATTEMPT, *LPRILIMSHANDOVERATTEMPT, RILIMSHANDOVERATTEMPT structure [Network Drivers Starting with Windows Vista], RILIMSHANDOVERATTEMPT, netvista.rilimshandoverattempt
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
-	RILIMSHANDOVERATTEMPT
product: Windows
targetos: Windows
req.typenames: "*LPRILIMSHANDOVERATTEMPT, RILIMSHANDOVERATTEMPT"
---

# RILIMSHANDOVERATTEMPT structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILIMSHANDOVERATTEMPT {
  DWORD             cbSize;
  RILIMSSYSTEMTYPE  dwOldSystemType;
  RILIMSSYSTEMTYPE  dwDestSystemType;
  HRESULT           hrHandOverResult;
} RILIMSHANDOVERATTEMPT, RILIMSHANDOVERATTEMPT;
````


## -struct-fields




#### - cbSize



#### - dwOldSystemType



#### - dwDestSystemType



#### - hrHandOverResult


