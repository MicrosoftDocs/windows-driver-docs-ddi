---
UID: NS:ntddrilapitypes.RILCBGWLCONFIGINFO
title: RILCBGWLCONFIGINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcbgwlconfiginfo.htm
old-project: netvista
ms.assetid: b92f6639-bf6a-4c1b-a0a6-57e310251591
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilcbgwlconfiginfo, *LPRILCBGWLCONFIGINFO, ntddrilapitypes/RILCBGWLCONFIGINFO, RILCBGWLCONFIGINFO, RILCBGWLCONFIGINFO structure [Network Drivers Starting with Windows Vista]
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
-	RILCBGWLCONFIGINFO
product: Windows
targetos: Windows
req.typenames: "*LPRILCBGWLCONFIGINFO, RILCBGWLCONFIGINFO"
---

# RILCBGWLCONFIGINFO structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILCBGWLCONFIGINFO {
  BOOL      fAccept;
  RILRANGE  rgrrBroadcastMsgID;
} RILCBGWLCONFIGINFO, RILCBGWLCONFIGINFO;
````


## -struct-fields




### -field fAccept


### -field rgrrBroadcastMsgID

