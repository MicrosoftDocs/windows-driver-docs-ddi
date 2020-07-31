---
UID: NF:dbgmodel.IDataModelScriptDebugBreakpoint.GetPosition
title: IDataModelScriptDebugBreakpoint::GetPosition (dbgmodel.h)
description: The GetPosition method returns the position of the breakpoint within the script.
ms.assetid: cdc328af-b80c-45cb-b4a1-5b31e878014e
ms.date: 09/10/2018
keywords: ["IDataModelScriptDebugBreakpoint::GetPosition"]
f1_keywords:
 - "dbgmodel/IDataModelScriptDebugBreakpoint.GetPosition"
 - "IDataModelScriptDebugBreakpoint.GetPosition"
ms.keywords: IDataModelScriptDebugBreakpoint::GetPosition, GetPosition, IDataModelScriptDebugBreakpoint.GetPosition, IDataModelScriptDebugBreakpoint::GetPosition, IDataModelScriptDebugBreakpoint.GetPosition
req.header: dbgmodel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- COM
api_location: 
- dbgmodel.h
api_name: 
- IDataModelScriptDebugBreakpoint.GetPosition
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptDebugBreakpoint::GetPosition


## -description

The GetPosition method returns the position of the breakpoint within the script. The script debugger must return the line and column within source code where the breakpoint is located. If it is capable of doing so, it can also return a span of source represented by the breakpoint by filling out an end position as defined by the positionSpanEnd argument. If the debugger is not capable of producing this span and the caller requests it, the Line and Column fields of the span's ending position should be filled in as zero indicating that the values cannot be provided. 

The debugger may also return the text of the line (or span) of source code where breakpoint exists in the lineText argument. While it is strongly recommended that debuggers return this value, it is not required. Only the line and column position within source are required return values. Should the debugger not be capable of producing the source text, nullptr may be returned in the lineText argument. 


## -parameters

### -param position
The line and column position of the breakpoint within the script's source code must be returned here.

### -param positionSpanEnd
If the debugger is capable of producing the span of source represented by the breakpoint, it can return the line and column positions of the end of the span here. If not, the Line and Column values of the structure should be set to zero indicating that the values cannot be provided..

### -param lineText
If the debugger can produce the line (or span) of source code represented by the breakpoint, it returns such here as a string allocated via the SysAllocString function. The caller is responsible for freeing the returned string via SysFreeString. If the debugger is not capable of returning this source text, nullptr should be returned here.


## -returns
This method returns HRESULT that indicates success or failure.
## -remarks

## -see-also

[IDataModelScriptDebugBreakpoint interface](nn-dbgmodel-idatamodelscriptdebugbreakpoint.md)
