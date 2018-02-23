---
UID: NS:d4iface._DOT4_ACTIVITY
title: "_DOT4_ACTIVITY"
author: windows-driver-content
description: "."
old-location: print\dot4_activity.htm
old-project: print
ms.assetid: CD3DBBA5-AE5C-4DC1-BE52-696138494701
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: "*PDOT4_ACTIVITY, PDOT4_ACTIVITY, d4iface/PDOT4_ACTIVITY, _DOT4_ACTIVITY, print.dot4_activity, d4iface/DOT4_ACTIVITY, DOT4_ACTIVITY structure [Print Devices], DOT4_ACTIVITY, PDOT4_ACTIVITY structure pointer [Print Devices]"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d4iface.h
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
-	D4iface.h
apiname:
-	DOT4_ACTIVITY
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# _DOT4_ACTIVITY structure


## -description





## -syntax


````
typedef struct _DOT4_ACTIVITY {
  ULONG          ulMessage;
  ULONG          ulByteCount;
  CHANNEL_HANDLE hChannel;
} DOT4_ACTIVITY, *PDOT4_ACTIVITY;
````


## -struct-fields




### -field ulMessage


### -field ulByteCount


### -field hChannel

