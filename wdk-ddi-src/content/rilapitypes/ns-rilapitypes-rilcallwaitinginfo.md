---
UID: NS:rilapitypes.RILCALLWAITINGINFO
title: RILCALLWAITINGINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallwaitinginfo_2.htm
old-project: netvista
ms.assetid: a634355a-c508-4f1b-9b8b-9325cb34cde0
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILCALLWAITINGINFO, *LPRILCALLWAITINGINFO, rilapitypes/RILCALLWAITINGINFO, netvista.rilcallwaitinginfo_2, RILCALLWAITINGINFO structure [Network Drivers Starting with Windows Vista]
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
-	RILCALLWAITINGINFO
product: Windows
targetos: Windows
req.typenames: RILCALLWAITINGINFO, *LPRILCALLWAITINGINFO
req.product: Windows 10 or later.
---

# RILCALLWAITINGINFO structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILCALLWAITINGINFO {
  DWORD               cbSize;
  DWORD               dwParams;
  DWORD               dwExecutor;
  RILCALLTYPE         dwCallType;
  RILREMOTEPARTYINFO  rrpiCallerInfo;
} RILCALLWAITINGINFO, RILCALLWAITINGINFO;
````


## -struct-fields




### -field cbSize



### -field dwParams



### -field dwExecutor



### -field dwCallType



### -field rrpiCallerInfo


