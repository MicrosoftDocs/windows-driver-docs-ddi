---
UID: NS:dbgeng._DEBUG_EXCEPTION_FILTER_PARAMETERS
title: _DEBUG_EXCEPTION_FILTER_PARAMETERS (dbgeng.h)
description: The DEBUG_EXCEPTION_FILTER_PARAMETERS structure contains the parameters for an exception filter.
old-location: debugger\debug_exception_filter_parameters.htm
tech.root: debugger
ms.assetid: 26a101c5-0866-44e3-948b-8d3ca4dd9d00
ms.date: 05/03/2018
keywords: ["_DEBUG_EXCEPTION_FILTER_PARAMETERS structure"]
ms.keywords: "*PDEBUG_EXCEPTION_FILTER_PARAMETERS, DEBUG_EXCEPTION_FILTER_PARAMETERS, DEBUG_EXCEPTION_FILTER_PARAMETERS structure [Windows Debugging], PDEBUG_EXCEPTION_FILTER_PARAMETERS, PDEBUG_EXCEPTION_FILTER_PARAMETERS structure pointer [Windows Debugging], Structures_f3f2b1ac-e10c-439e-9de9-6b4161bf3c28.xml, _DEBUG_EXCEPTION_FILTER_PARAMETERS, dbgeng/DEBUG_EXCEPTION_FILTER_PARAMETERS, dbgeng/PDEBUG_EXCEPTION_FILTER_PARAMETERS, debugger.debug_exception_filter_parameters"
f1_keywords:
 - "dbgeng/DEBUG_EXCEPTION_FILTER_PARAMETERS"
 - "DEBUG_EXCEPTION_FILTER_PARAMETERS"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- DbgEng.h
api_name:
- DEBUG_EXCEPTION_FILTER_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: DEBUG_EXCEPTION_FILTER_PARAMETERS, *PDEBUG_EXCEPTION_FILTER_PARAMETERS
---

# _DEBUG_EXCEPTION_FILTER_PARAMETERS structure


## -description


The DEBUG_EXCEPTION_FILTER_PARAMETERS structure contains the parameters for an exception filter.


## -struct-fields




### -field ExecutionOption

The <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-filter-xxx">break status</a> of the exception filter, including the terminator.  For possible values, see <b>DEBUG_FILTER_XXX</b>.


### -field ContinueOption

The <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-filter-xxx">handling status</a> of the exception filter.  For possible values, see <b>DEBUG_FILTER_XXX</b>.


### -field TextSize

The size, in characters, of the name (including the terminator) of the exception filter.  If the filter is an arbitrary exception filter, it does not have a name and <b>TextSize</b> is zero.


### -field CommandSize

The size, in characters, of the command (including the terminator) to execute upon the first chance of the exception.


### -field SecondCommandSize

The size, in characters, of the command (including the terminator) to execute upon the second chance of the exception.


### -field ExceptionCode

The exception code for the exception filter.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getexceptionfilterparameters">GetExceptionFilterParameters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setexceptionfilterparameters">SetExceptionFilterParameters</a>
 

 

