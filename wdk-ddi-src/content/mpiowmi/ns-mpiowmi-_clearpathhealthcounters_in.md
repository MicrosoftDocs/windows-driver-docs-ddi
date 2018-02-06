---
UID: NS:mpiowmi._ClearPathHealthCounters_IN
title: "_ClearPathHealthCounters_IN"
author: windows-driver-content
description: The ClearPathHealthCounters_IN structure is used to provide an input parameter to the ClearPathHealthCounters method.
old-location: storage\clearpathhealthcounters_in.htm
old-project: storage
ms.assetid: 12c4462a-886b-4446-ace4-128af0af5dc0
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: mpiowmi/PClearPathHealthCounters_IN, PClearPathHealthCounters_IN structure pointer [Storage Devices], structs-scsibus_c1039fbb-d682-4fe8-a1ee-8fe7f7a0d1fc.xml, _ClearPathHealthCounters_IN, mpiowmi/ClearPathHealthCounters_IN, storage.clearpathhealthcounters_in, ClearPathHealthCounters_IN structure [Storage Devices], ClearPathHealthCounters_IN, PClearPathHealthCounters_IN, *PClearPathHealthCounters_IN
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
-	ClearPathHealthCounters_IN
product: Windows
targetos: Windows
req.typenames: ClearPathHealthCounters_IN, *PClearPathHealthCounters_IN
---

# _ClearPathHealthCounters_IN structure


## -description


The ClearPathHealthCounters_IN structure is used to provide an input parameter to the ClearPathHealthCounters method.


## -syntax


````
typedef struct _ClearPathHealthCounters_IN {
  ULONGLONG PathID;
} ClearPathHealthCounters_IN, *PClearPathHealthCounters_IN;
````


## -struct-fields




### -field PathID

A 64-bitfield that specifies the path that is associated with the device.

