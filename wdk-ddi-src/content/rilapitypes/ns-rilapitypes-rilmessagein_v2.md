---
UID: NS:rilapitypes.RILMESSAGEIN_V2
title: RILMESSAGEIN_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessagein_v2_2.htm
old-project: netvista
ms.assetid: a800eaf5-249e-4f17-9584-55dc6deb7bff
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilmessagein_v2_2, rilapitypes/RILMESSAGEIN_V2, RILMESSAGEIN_V2, RILMESSAGEIN, RILMESSAGEIN_V2 structure [Network Drivers Starting with Windows Vista], *LPRILMESSAGEIN
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
-	RILMESSAGEIN_V2
product: Windows
targetos: Windows
req.typenames: *LPRILMESSAGEIN, RILMESSAGEIN, RILMESSAGEIN_V2
req.product: Windows 10 or later.
---

# RILMESSAGEIN_V2 structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILMESSAGEIN_V2 {
  DWORD       cbSize;
  DWORD       dwExecutor;
  HUICCAPP    hUiccApp;
  DWORD       dwAckID;
  RILMESSAGE  rm;
  DWORD       dwFlags;
} RILMESSAGEIN_V2, RILMESSAGEIN_V2;
````


## -struct-fields




### -field cbSize



### -field dwExecutor



### -field hUiccApp



### -field dwAckID



### -field rm



### -field dwFlags


