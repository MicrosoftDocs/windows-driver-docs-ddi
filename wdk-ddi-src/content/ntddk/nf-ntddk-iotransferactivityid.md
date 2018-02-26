---
UID: NF:ntddk.IoTransferActivityId
title: IoTransferActivityId function
author: windows-driver-content
description: The IoTransferActivityId routine logs an ETW transfer event using the I/O tracing provider on behalf of the caller. This allows a driver to associate two related activity IDs without requiring a specific provider to be enabled.
old-location: kernel\iotransferactivityid.htm
old-project: kernel
ms.assetid: BA6EBD60-B7D8-4EDE-A655-2F18F27E6299
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , A, I, IoTransferActivityId, IoTransferActivityId routine [Kernel-Mode Driver Architecture], T, a, c, d, e, f, i, kernel.iotransferactivityid, n, ntddk/IoTransferActivityId, o, r, s, t, v, y"
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
-	IoTransferActivityId
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoTransferActivityId function


## -description


The IoTransferActivityId routine logs an ETW transfer event using the I/O tracing provider on behalf of the caller.  This allows a driver to associate two related activity IDs without requiring a specific provider to be enabled.


## -syntax


````
void IoTransferActivityId(
  _In_ LPCGUID ActivityId,
  _In_ LPCGUID RelatedActivityId
);
````


## -parameters




### -param ActivityId [in]

The source activity ID.


### -param RelatedActivityId [in]

The new activity ID to be transferred from the source activity ID.


## -returns



None.



