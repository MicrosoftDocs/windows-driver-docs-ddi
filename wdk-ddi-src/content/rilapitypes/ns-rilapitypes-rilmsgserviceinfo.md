---
UID: NS:rilapitypes.RILMSGSERVICEINFO
title: RILMSGSERVICEINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgserviceinfo_2.htm
old-project: netvista
ms.assetid: a6d5bc57-dd0e-4a75-af48-470b65e70a7d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILMSGSERVICEINFO structure [Network Drivers Starting with Windows Vista], RILMSGSERVICEINFO, netvista.rilmsgserviceinfo_2, *LPRILMSGSERVICEINFO, rilapitypes/RILMSGSERVICEINFO
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
-	RILMSGSERVICEINFO
product: Windows
targetos: Windows
req.typenames: "*LPRILMSGSERVICEINFO, RILMSGSERVICEINFO"
req.product: Windows 10 or later.
---

# RILMSGSERVICEINFO structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILMSGSERVICEINFO {
  DWORD  cbSize;
  DWORD  dwParams;
  DWORD  dwMsgSupport;
  DWORD  dwStoreUsed;
  DWORD  dwStoreTotal;
} RILMSGSERVICEINFO, RILMSGSERVICEINFO;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwMsgSupport


### -field dwStoreUsed


### -field dwStoreTotal

