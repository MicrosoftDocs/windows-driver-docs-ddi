---
UID: NS:ntddrilapitypes.RILMESSAGEINFO
title: RILMESSAGEINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessageinfo.htm
old-project: netvista
ms.assetid: 689b4abc-13ee-4d4a-8b2e-bb0be7cc6672
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RILMESSAGEINFO, netvista.rilmessageinfo, RILMESSAGEINFO structure [Network Drivers Starting with Windows Vista], *LPRILMESSAGEINFO, RILMESSAGEINFO
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
-	RILMESSAGEINFO
product: Windows
targetos: Windows
req.typenames: "*LPRILMESSAGEINFO, RILMESSAGEINFO"
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

