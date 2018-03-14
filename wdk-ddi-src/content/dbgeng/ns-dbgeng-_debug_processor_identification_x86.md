---
UID: NS:dbgeng._DEBUG_PROCESSOR_IDENTIFICATION_X86
title: "_DEBUG_PROCESSOR_IDENTIFICATION_X86"
author: windows-driver-content
description: Identifies an x86 processor.
old-location: debugger\debug_processor_identification_x86.htm
old-project: debugger
ms.assetid: B5AD9CE8-B0F0-49BC-984E-4372FD3BF93B
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PDEBUG_PROCESSOR_IDENTIFICATION_X86, DEBUG_PROCESSOR_IDENTIFICATION_X86, DEBUG_PROCESSOR_IDENTIFICATION_X86 structure [Windows Debugging], PDEBUG_PROCESSOR_IDENTIFICATION_X86, PDEBUG_PROCESSOR_IDENTIFICATION_X86 structure pointer [Windows Debugging], _DEBUG_PROCESSOR_IDENTIFICATION_X86, dbgeng/DEBUG_PROCESSOR_IDENTIFICATION_X86, dbgeng/PDEBUG_PROCESSOR_IDENTIFICATION_X86, debugger.debug_processor_identification_x86"
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
-	DEBUG_PROCESSOR_IDENTIFICATION_X86
product: Windows
targetos: Windows
req.typenames: DEBUG_PROCESSOR_IDENTIFICATION_X86, *PDEBUG_PROCESSOR_IDENTIFICATION_X86
---

# _DEBUG_PROCESSOR_IDENTIFICATION_X86 structure


## -description


Identifies an x86 processor. 


## -syntax


````
typedef struct _DEBUG_PROCESSOR_IDENTIFICATION_X86 {
  ULONG Family;
  ULONG Model;
  ULONG Stepping;
  CHAR  VendorString[16];
} DEBUG_PROCESSOR_IDENTIFICATION_X86, *PDEBUG_PROCESSOR_IDENTIFICATION_X86;
````


## -struct-fields




### -field Family

The family of the processor.


### -field Model

The model of the processor.


### -field Stepping

The stepping value of the processor.


### -field VendorString

A vendor specified string.


## -see-also

<a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_all.md">DEBUG_PROCESSOR_IDENTIFICATION_ALL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20DEBUG_PROCESSOR_IDENTIFICATION_X86 structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

