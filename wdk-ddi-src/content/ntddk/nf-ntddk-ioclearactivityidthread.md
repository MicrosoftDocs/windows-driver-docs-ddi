---
UID: NF:ntddk.IoClearActivityIdThread
title: IoClearActivityIdThread function
author: windows-driver-content
description: The IoClearActivityIdThread routine clears the activity ID of the current thread.
old-location: kernel\ioclearactivityidthread.htm
old-project: kernel
ms.assetid: 2F69FC2F-C336-4B51-8EFC-0A9AA22121B9
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoClearActivityIdThread routine [Kernel-Mode Driver Architecture], kernel.ioclearactivityidthread, ntddk/IoClearActivityIdThread, IoClearActivityIdThread
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
-	IoClearActivityIdThread
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---

# IoClearActivityIdThread function


## -description


The IoClearActivityIdThread routine clears the activity ID of the current thread.


## -syntax


````
void IoClearActivityIdThread(
  _In_ LPCGUID OriginalId
);
````


## -parameters




### -param OriginalId [in]

The activity ID that was previously set on the thread.


## -returns



None.



