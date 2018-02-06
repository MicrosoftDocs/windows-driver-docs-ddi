---
UID: NS:dbgeng._DEBUG_PROCESSOR_IDENTIFICATION_ALPHA
title: "_DEBUG_PROCESSOR_IDENTIFICATION_ALPHA"
author: windows-driver-content
description: Identifies an Alpha processor.
old-location: debugger\debug_processor_identification_alpha.htm
old-project: debugger
ms.assetid: AE0DB2CC-6364-4B50-8CD3-8EF8B495FBED
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: dbgeng/DEBUG_PROCESSOR_IDENTIFICATION_ALPHA, PDEBUG_PROCESSOR_IDENTIFICATION_ALPHA, _DEBUG_PROCESSOR_IDENTIFICATION_ALPHA, PDEBUG_PROCESSOR_IDENTIFICATION_ALPHA structure pointer [Windows Debugging], DEBUG_PROCESSOR_IDENTIFICATION_ALPHA structure [Windows Debugging], dbgeng/PDEBUG_PROCESSOR_IDENTIFICATION_ALPHA, DEBUG_PROCESSOR_IDENTIFICATION_ALPHA, debugger.debug_processor_identification_alpha, *PDEBUG_PROCESSOR_IDENTIFICATION_ALPHA
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	DbgEng.h
apiname:
-	DEBUG_PROCESSOR_IDENTIFICATION_ALPHA
product: Windows
targetos: Windows
req.typenames: "*PDEBUG_PROCESSOR_IDENTIFICATION_ALPHA, DEBUG_PROCESSOR_IDENTIFICATION_ALPHA"
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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20DEBUG_PROCESSOR_IDENTIFICATION_ALPHA structure%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

