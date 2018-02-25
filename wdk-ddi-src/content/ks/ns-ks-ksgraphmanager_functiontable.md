---
UID: NS:ks.KSGRAPHMANAGER_FUNCTIONTABLE
title: KSGRAPHMANAGER_FUNCTIONTABLE
author: windows-driver-content
description: "."
old-location: stream\ksgraphmanager_functiontable.htm
old-project: stream
ms.assetid: F077B970-F146-43BC-BB92-A836C8843890
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, A, B, C, E, F, G, H, I, K, KSGRAPHMANAGER_FUNCTIONTABLE, KSGRAPHMANAGER_FUNCTIONTABLE structure [Streaming Media Devices], L, M, N, O, P, PKSGRAPHMANAGER_FUNCTIONTABLE, PKSGRAPHMANAGER_FUNCTIONTABLE structure [Streaming Media Devices], R, S, T, U, _, ks/KSGRAPHMANAGER_FUNCTIONTABLE, ks/PKSGRAPHMANAGER_FUNCTIONTABLE, stream.ksgraphmanager_functiontable"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
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
-	Ks.h
apiname:
-	KSGRAPHMANAGER_FUNCTIONTABLE
product: Windows
targetos: Windows
req.typenames: KSGRAPHMANAGER_FUNCTIONTABLE, PKSGRAPHMANAGER_FUNCTIONTABLE
---

# KSGRAPHMANAGER_FUNCTIONTABLE structure


## -description





## -syntax


````
typedef struct _KSGRAPHMANAGER_FUNCTIONTABLE {
  PFNKSGRAPHMANAGER_NOTIFY NotifyEvent;
} KSGRAPHMANAGER_FUNCTIONTABLE, PKSGRAPHMANAGER_FUNCTIONTABLE;
````


## -struct-fields




### -field NotifyEvent

