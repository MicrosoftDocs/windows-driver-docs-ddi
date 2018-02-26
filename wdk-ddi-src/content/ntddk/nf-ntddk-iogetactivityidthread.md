---
UID: NF:ntddk.IoGetActivityIdThread
title: IoGetActivityIdThread function
author: windows-driver-content
description: The IoGetActivityIdThread routine returns the activity ID associated with the current thread.
old-location: kernel\iogetactivityidthread.htm
old-project: kernel
ms.assetid: 445A9EBA-EF15-4FE4-9747-3E1E138E13E7
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , A, G, I, IoGetActivityIdThread, IoGetActivityIdThread routine [Kernel-Mode Driver Architecture], T, a, c, d, e, h, i, kernel.iogetactivityidthread, ntddk/IoGetActivityIdThread, o, r, t, v, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows 8.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoGetActivityIdThread
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoGetActivityIdThread function


## -description


The IoGetActivityIdThread routine returns the activity ID associated with the current thread.


## -syntax


````
LPCGUID IoGetActivityIdThread(
    None.
);
````


## -parameters






##### - None.


## -returns



The activity ID associated with the current thread.



