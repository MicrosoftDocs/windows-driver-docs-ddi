---
UID: NS:winsplp._SPLCLIENT_INFO_2_V3
title: "_SPLCLIENT_INFO_2_V3"
author: windows-driver-content
description: "."
old-location: print\splclient_info_2_longhorn.htm
old-project: print
ms.assetid: D058EF0A-014A-4A91-A8B5-6D4ACB1667E0
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: "*PSPLCLIENT_INFO_2, SPLCLIENT_INFO_2, winsplp/SPLCLIENT_INFO_2_LONGHORN, SPLCLIENT_INFO_2_LONGHORN structure [Print Devices], print.splclient_info_2_longhorn, *LPSPLCLIENT_INFO_2, _SPLCLIENT_INFO_2_V3, SPLCLIENT_INFO_2_LONGHORN"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winsplp.h
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
-	Winsplp.h
apiname:
-	SPLCLIENT_INFO_2_LONGHORN
product: Windows
targetos: Windows
req.typenames: SPLCLIENT_INFO_2_LONGHORN
req.product: Windows 10 or later.
---

# _SPLCLIENT_INFO_2_V3 structure


## -description





## -syntax


````
typedef struct _SPLCLIENT_INFO_2_V3 {
  UINT64           hSplPrinter;
} SPLCLIENT_INFO_2_LONGHORN;
````


## -struct-fields




### -field hSplPrinter

Specifies the server-side handle to be used for direct calls.

