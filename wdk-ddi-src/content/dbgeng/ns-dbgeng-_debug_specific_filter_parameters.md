---
UID: NS:dbgeng._DEBUG_SPECIFIC_FILTER_PARAMETERS
title: _DEBUG_SPECIFIC_FILTER_PARAMETERS (dbgeng.h)
description: The DEBUG_SPECIFIC_FILTER_PARAMETERS structure contains the parameters for a specific event filter.
old-location: debugger\debug_specific_filter_parameters.htm
tech.root: debugger
ms.assetid: 06926380-aae5-4d9f-94e0-43098f8a0423
ms.date: 05/03/2018
keywords: ["DEBUG_SPECIFIC_FILTER_PARAMETERS structure"]
ms.keywords: "*PDEBUG_SPECIFIC_FILTER_PARAMETERS, DEBUG_SPECIFIC_FILTER_PARAMETERS, DEBUG_SPECIFIC_FILTER_PARAMETERS structure [Windows Debugging], PDEBUG_SPECIFIC_FILTER_PARAMETERS, PDEBUG_SPECIFIC_FILTER_PARAMETERS structure pointer [Windows Debugging], Structures_b0152b9b-4809-46c8-81a7-5f571720eca1.xml, _DEBUG_SPECIFIC_FILTER_PARAMETERS, dbgeng/DEBUG_SPECIFIC_FILTER_PARAMETERS, dbgeng/PDEBUG_SPECIFIC_FILTER_PARAMETERS, debugger.debug_specific_filter_parameters"
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
targetos: Windows
req.typenames: DEBUG_SPECIFIC_FILTER_PARAMETERS, *PDEBUG_SPECIFIC_FILTER_PARAMETERS
f1_keywords:
 - _DEBUG_SPECIFIC_FILTER_PARAMETERS
 - dbgeng/_DEBUG_SPECIFIC_FILTER_PARAMETERS
 - PDEBUG_SPECIFIC_FILTER_PARAMETERS
 - dbgeng/PDEBUG_SPECIFIC_FILTER_PARAMETERS
 - DEBUG_SPECIFIC_FILTER_PARAMETERS
 - dbgeng/DEBUG_SPECIFIC_FILTER_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - DbgEng.h
api_name:
 - DEBUG_SPECIFIC_FILTER_PARAMETERS
---

# _DEBUG_SPECIFIC_FILTER_PARAMETERS structure


## -description

The DEBUG_SPECIFIC_FILTER_PARAMETERS structure contains the parameters for a <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-filter-xxx">specific event filter</a>.

## -struct-fields

### -field ExecutionOption

The <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-filter-xxx">break status</a> of the specific event filter.  For possible values, see <b>DEBUG_FILTER_XXX</b>.

### -field ContinueOption

The <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-filter-xxx">handling status</a> of the specific event filter.  For possible values, see <b>DEBUG_FILTER_XXX</b>.

### -field TextSize

The size, in characters (including the terminator), of the name of the specific event filter.

### -field CommandSize

The size, in characters, of the command (including the terminator), to execute when the event occurs.

### -field ArgumentSize

Specifies the size, in characters, of the specific event filter argument.  This size includes the NULL terminator.  If the specific event filter does not take an argument, <b>ArgumentSize</b> is zero.

<div class="alert"><b>Note</b>  If the filter does take an argument, but the argument is empty, <b>ArgumentSize</b> will be one, reflecting the NULL terminator.</div>
<div> </div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getspecificfilterparameters">GetSpecificFilterParameters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setspecificfilterparameters">SetSpecificFilterParameters</a>

