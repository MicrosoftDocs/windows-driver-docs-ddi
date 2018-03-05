---
UID: NS:winsplp._PRINTER_NOTIFY_INIT
title: "_PRINTER_NOTIFY_INIT"
author: windows-driver-content
description: "."
old-location: print\printer_notify_init.htm
old-project: print
ms.assetid: 45DFA669-8520-4EA5-8B36-822BDC8C958D
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPPRINTER_NOTIFY_INIT, *PPRINTER_NOTIFY_INIT, LPPRINTER_NOTIFY_INIT, LPPRINTER_NOTIFY_INIT structure pointer [Print Devices], PPRINTER_NOTIFY_INIT, PPRINTER_NOTIFY_INIT structure pointer [Print Devices], PRINTER_NOTIFY_INIT, PRINTER_NOTIFY_INIT structure [Print Devices], _PRINTER_NOTIFY_INIT, print.printer_notify_init, winsplp/LPPRINTER_NOTIFY_INIT, winsplp/PPRINTER_NOTIFY_INIT, winsplp/PRINTER_NOTIFY_INIT"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Winsplp.h
api_name:
-	PRINTER_NOTIFY_INIT
product: Windows
targetos: Windows
req.typenames: PRINTER_NOTIFY_INIT, *PPRINTER_NOTIFY_INIT, *LPPRINTER_NOTIFY_INIT
req.product: Windows 10 or later.
---

# _PRINTER_NOTIFY_INIT structure


## -description





## -syntax


````
typedef struct _PRINTER_NOTIFY_INIT {
  DWORD Size;
  DWORD Reserved;
  DWORD PollTime;
} PRINTER_NOTIFY_INIT, *PPRINTER_NOTIFY_INIT, *LPPRINTER_NOTIFY_INIT;
````


## -struct-fields




### -field Size


### -field Reserved


### -field PollTime

