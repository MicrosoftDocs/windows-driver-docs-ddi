---
UID: NS:mpiowmi._ClearMpioDiskHealthCounters_IN
title: "_ClearMpioDiskHealthCounters_IN"
author: windows-driver-content
description: The ClearMpioDiskHealthCounters_IN structure is used to provide an input parameter to the ClearMpioDiskHealthCounters method.
old-location: storage\clearmpiodiskhealthcounters_in.htm
old-project: storage
ms.assetid: 1af28545-f43f-47a2-b6a2-64fd7a408687
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PClearMpioDiskHealthCounters_IN, ,, C, ClearMpioDiskHealthCounters_IN, ClearMpioDiskHealthCounters_IN structure [Storage Devices], D, H, I, M, N, P, PClearMpioDiskHealthCounters_IN, PClearMpioDiskHealthCounters_IN structure pointer [Storage Devices], _, _ClearMpioDiskHealthCounters_IN, a, e, h, i, k, l, mpiowmi/ClearMpioDiskHealthCounters_IN, mpiowmi/PClearMpioDiskHealthCounters_IN, n, o, p, r, s, storage.clearmpiodiskhealthcounters_in, structs-scsibus_52663a43-dc66-4b77-b30d-d60ffbea7232.xml, t, u"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: mpiowmi.h
req.include-header: Mpiowmi.h
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
-	mpiowmi.h
apiname:
-	ClearMpioDiskHealthCounters_IN
product: Windows
targetos: Windows
req.typenames: ClearMpioDiskHealthCounters_IN, *PClearMpioDiskHealthCounters_IN
---

# _ClearMpioDiskHealthCounters_IN structure


## -description


The ClearMpioDiskHealthCounters_IN structure is used to provide an input parameter to the ClearMpioDiskHealthCounters method.


## -syntax


````
typedef struct _ClearMpioDiskHealthCounters_IN {
  ULONG DiskOrdinal;
} ClearMpioDiskHealthCounters_IN, *PClearMpioDiskHealthCounters_IN;
````


## -struct-fields




### -field DiskOrdinal

A 32-bitfield that represents the MPIO disk ordinal value.

