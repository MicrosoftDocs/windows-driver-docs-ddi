---
UID: NS:dbgeng._STACK_SYM_FRAME_INFO
title: "_STACK_SYM_FRAME_INFO"
author: windows-driver-content
description: Defines stack source information for an extended stack frame.
old-location: debugger\stack_sym_frame_info.htm
old-project: debugger
ms.assetid: 1DE23CF6-970E-4BDE-9BEC-CAC0640B257A
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: "*PSTACK_SYM_FRAME_INFO, PSTACK_SYM_FRAME_INFO, PSTACK_SYM_FRAME_INFO structure pointer [Windows Debugging], STACK_SYM_FRAME_INFO, STACK_SYM_FRAME_INFO structure [Windows Debugging], _STACK_SYM_FRAME_INFO, dbgeng/PSTACK_SYM_FRAME_INFO, dbgeng/STACK_SYM_FRAME_INFO, debugger.stack_sym_frame_info"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dbgeng.h
api_name:
-	STACK_SYM_FRAME_INFO
product: Windows
targetos: Windows
req.typenames: STACK_SYM_FRAME_INFO, *PSTACK_SYM_FRAME_INFO
---

# _STACK_SYM_FRAME_INFO structure


## -description


Defines stack source information for an extended stack frame. 


## -struct-fields




### -field StackFrameEx

A stack frame as a <a href="https://msdn.microsoft.com/library/windows/hardware/dn818561">DEBUG_STACK_FRAME_EX</a> structure. 


### -field SrcInfo

Stack source information as a <a href="https://msdn.microsoft.com/F19D5A5C-D9CF-40CC-B344-8F2D862FBF04">STACK_SRC_INFO</a> structure.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn818561">DEBUG_STACK_FRAME_EX</a>



<a href="https://msdn.microsoft.com/F19D5A5C-D9CF-40CC-B344-8F2D862FBF04">STACK_SRC_INFO</a>
 

 

