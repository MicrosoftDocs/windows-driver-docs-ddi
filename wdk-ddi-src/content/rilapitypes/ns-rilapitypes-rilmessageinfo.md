---
UID: NS:rilapitypes.RILMESSAGEINFO
title: RILMESSAGEINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessageinfo_2.htm
old-project: netvista
ms.assetid: db7b8526-e70a-4589-a128-58641c865d58
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILMESSAGEINFO, RILMESSAGEINFO, RILMESSAGEINFO structure [Network Drivers Starting with Windows Vista], netvista.rilmessageinfo_2, rilapitypes/RILMESSAGEINFO"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILMESSAGEINFO
product: Windows
targetos: Windows
req.typenames: RILMESSAGEINFO, *LPRILMESSAGEINFO
req.product: Windows 10 or later.
---

# RILMESSAGEINFO structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILMESSAGEINFO {
  DWORD             cbSize;
  HUICCAPP          hUiccApp;
  DWORD             dwParams;
  DWORD             dwIndex;
  RILMESSAGESTATUS  dwStatus;
  RILMESSAGE        rmMessage;
} RILMESSAGEINFO, RILMESSAGEINFO;
````


## -struct-fields




### -field cbSize


### -field hUiccApp


### -field dwParams


### -field dwIndex


### -field dwStatus


### -field rmMessage

