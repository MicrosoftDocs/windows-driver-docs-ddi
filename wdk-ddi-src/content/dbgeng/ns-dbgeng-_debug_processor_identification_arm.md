---
UID: NS:dbgeng._DEBUG_PROCESSOR_IDENTIFICATION_ARM
title: "_DEBUG_PROCESSOR_IDENTIFICATION_ARM"
author: windows-driver-content
description: Identifies an ARM processor.
old-location: debugger\debug_processor_identification_arm.htm
old-project: debugger
ms.assetid: 4C7D5959-7900-4482-A45C-61D66541C276
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PDEBUG_PROCESSOR_IDENTIFICATION_ARM, DEBUG_PROCESSOR_IDENTIFICATION_ARM, DEBUG_PROCESSOR_IDENTIFICATION_ARM structure [Windows Debugging], PDEBUG_PROCESSOR_IDENTIFICATION_ARM, PDEBUG_PROCESSOR_IDENTIFICATION_ARM structure pointer [Windows Debugging], _DEBUG_PROCESSOR_IDENTIFICATION_ARM, dbgeng/DEBUG_PROCESSOR_IDENTIFICATION_ARM, dbgeng/PDEBUG_PROCESSOR_IDENTIFICATION_ARM, debugger.debug_processor_identification_arm"
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
-	DEBUG_PROCESSOR_IDENTIFICATION_ARM
product: Windows
targetos: Windows
req.typenames: DEBUG_PROCESSOR_IDENTIFICATION_ARM, *PDEBUG_PROCESSOR_IDENTIFICATION_ARM
---

# _DEBUG_PROCESSOR_IDENTIFICATION_ARM structure


## -description


Identifies an ARM processor. 


## -syntax


````
typedef struct _DEBUG_PROCESSOR_IDENTIFICATION_ARM {
  ULONG Model;
  ULONG Revision;
  CHAR  VendorString[16];
} DEBUG_PROCESSOR_IDENTIFICATION_ARM, *PDEBUG_PROCESSOR_IDENTIFICATION_ARM;
````


## -struct-fields




### -field Model

The model of the processor.


### -field Revision

The revision of the processor.


### -field VendorString

A vendor specified string.


## -see-also

<a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_all.md">DEBUG_PROCESSOR_IDENTIFICATION_ALL</a>



 

 


