---
UID: NF:dbgmodel.IDataModelScriptDebug2.GetCurrentPosition
title: IDataModelScriptDebug2::GetCurrentPosition (dbgmodel.h)
description: The GetCurrentPosition' method returns the current position within the script. 
ms.assetid: 3e84abeb-e856-4b29-a6ae-ea0a1ab31b27
ms.date: 08/21/2018
ms.topic: method
ms.keywords: IDataModelScriptDebug2::GetCurrentPosition, GetCurrentPosition, IDataModelScriptDebug2.GetCurrentPosition, IDataModelScriptDebug2::GetCurrentPosition, IDataModelScriptDebug2.GetCurrentPosition
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
-	apiref
api_type: 
-	COM
api_location: 
-	dbgmodel.h
api_name: 
-	IDataModelScriptDebug2.GetCurrentPosition
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptDebug2::GetCurrentPosition


## -description
The GetCurrentPosition' method returns the current position within the script. This may only be called when the script is broken into the debugger where a call to GetScriptState would return ScriptDebugBreak. Any other call to this method is invalid and will fail. 

The position of the script is defined as a span of characters. The start of the span must always be returned (both the line and column numbers). If the particular debugger is capable of returning the full span of the "current position" within the script, an ending position can optionally be returned in the positionSpanEnd argument. If the debugger is not capable of this, the line and column values in the span end (if requested) should be set to zero. 

If the debugger can pass the source code for the line of code where the debugger is broken, it may return such from this method. If possible, it is strongly encouraged to provide this information. There is, however, no requirement that any more information than the starting line and column of the break position is returned. If source line information is not supported, a nullptr value may be returned for that argument. 


## -parameters

### -param currentPosition
The current break position of the script must be returned here. The Line and Column fields of the returned structure are one based. A zero value in either indicates that the information is unavailable.

### -param positionSpanEnd
If the debugger is capable of determining the full span of the break position, the ending position of the span can be returned here. If not, zero values should be filled into the Line and Column fields of the returned structure.

### -param lineText
If the debugger is capable of returning the source code for the line (or the span) of the break, such can be returned here as a string allocated by the SysAllocString function. The caller is responsible for freeing the returned string with SysFreeString. If the debugger is incapable of producing this source information, nullptr should be returned.

## -returns
This method returns HRESULT that indicates success or failure.

## -see-also

[IDataModelScriptDebug2 interface](nn-dbgmodel-idatamodelscriptdebug2.md)
