---
UID: NS:dbgeng._DEBUG_PROCESSOR_IDENTIFICATION_ALPHA
title: "_DEBUG_PROCESSOR_IDENTIFICATION_ALPHA"
author: windows-driver-content
description: Identifies an Alpha processor.
old-location: debugger\debug_processor_identification_alpha.htm
old-project: debugger
ms.assetid: AE0DB2CC-6364-4B50-8CD3-8EF8B495FBED
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PDEBUG_PROCESSOR_IDENTIFICATION_ALPHA, DEBUG_PROCESSOR_IDENTIFICATION_ALPHA, DEBUG_PROCESSOR_IDENTIFICATION_ALPHA structure [Windows Debugging], PDEBUG_PROCESSOR_IDENTIFICATION_ALPHA, PDEBUG_PROCESSOR_IDENTIFICATION_ALPHA structure pointer [Windows Debugging], _DEBUG_PROCESSOR_IDENTIFICATION_ALPHA, dbgeng/DEBUG_PROCESSOR_IDENTIFICATION_ALPHA, dbgeng/PDEBUG_PROCESSOR_IDENTIFICATION_ALPHA, debugger.debug_processor_identification_alpha"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dbgeng.h
req.include-header: DbgEng.h
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
-	DbgEng.h
api_name:
-	DEBUG_PROCESSOR_IDENTIFICATION_ALPHA
product: Windows
targetos: Windows
req.typenames: DEBUG_PROCESSOR_IDENTIFICATION_ALPHA, *PDEBUG_PROCESSOR_IDENTIFICATION_ALPHA
---

# _DEBUG_PROCESSOR_IDENTIFICATION_ALPHA structure


## -description


Identifies an Alpha processor.


## -syntax


````
typedef struct _DEBUG_PROCESSOR_IDENTIFICATION_ALPHA {
  ULONG Type;
  ULONG Revision;
} DEBUG_PROCESSOR_IDENTIFICATION_ALPHA, *PDEBUG_PROCESSOR_IDENTIFICATION_ALPHA;
````


## -struct-fields




### -field Type

The type of the processor.


### -field Revision

The revision of the processor.


## -see-also

<a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_all.md">DEBUG_PROCESSOR_IDENTIFICATION_ALL</a>



 

 


