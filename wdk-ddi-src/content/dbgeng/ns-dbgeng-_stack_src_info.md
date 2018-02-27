---
UID: NS:dbgeng._STACK_SRC_INFO
title: "_STACK_SRC_INFO"
author: windows-driver-content
description: Defines stack source information.
old-location: debugger\stack_src_info.htm
old-project: debugger
ms.assetid: F19D5A5C-D9CF-40CC-B344-8F2D862FBF04
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PSTACK_SRC_INFO, PSTACK_SRC_INFO, PSTACK_SRC_INFO structure pointer [Windows Debugging], STACK_SRC_INFO, STACK_SRC_INFO structure [Windows Debugging], _STACK_SRC_INFO, dbgeng/PSTACK_SRC_INFO, dbgeng/STACK_SRC_INFO, debugger.stack_src_info"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
-	dbgeng.h
apiname:
-	STACK_SRC_INFO
product: Windows
targetos: Windows
req.typenames: STACK_SRC_INFO, *PSTACK_SRC_INFO
---

# _STACK_SRC_INFO structure


## -description


Defines stack source information. 


## -syntax


````
typedef struct _STACK_SRC_INFO {
  PCWSTR ImagePath;
  PCWSTR ModuleName;
  PCWSTR Function;
  ULONG  Displacement;
  ULONG  Row;
  ULONG  Column;
} STACK_SRC_INFO, *PSTACK_SRC_INFO;
````


## -struct-fields




### -field ImagePath

An image path.


### -field ModuleName

A module name.


### -field Function

A function.


### -field Displacement

A displacement value. 


### -field Row

A row number.


### -field Column

A column number.

