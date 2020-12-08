---
UID: NN:dbgmodel.IDataModelScriptDebug
title: IDataModelScriptDebug (dbgmodel.h)
description: The core interface that a script provider must provide in order to make a script debuggable.
ms.date: 10/04/2018
keywords: ["IDataModelScriptDebug interface"]
req.header: dbgmodel.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IDataModelScriptDebug
 - dbgmodel/IDataModelScriptDebug
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelScriptDebug
---

# IDataModelScriptDebug interface


## -description

The core interface that a script provider must provide in order to make a script debuggable. The implementation class of the [IDataModelScript](nn-dbgmodel-idatamodelscript.md) interface must QueryInterface for IDataModelScriptDebug if the script is debuggable.

Any script which is debuggable indicates this capability via the presence of the IDataModelScriptDebug interface on the same component which implements [IDataModelScript](nn-dbgmodel-idatamodelscript.md). The query for this interface by the debug host or the debugger application hosting the data model is what indicates the presence of the debug capability.

## -inheritance

IDataModelScriptDebug interits from IUnknown.

## -remarks

The infrastructure for script providers in the data model also provides a concept around debugging scripts. Any script that wishes to expose debugging capabilities to the debug host and the debugger application hosting the data model can do so by having debuggable scripts implement the IDataModelScriptDebug interface in addition to the [IDataModelScript](nn-dbgmodel-idatamodelscript.md) interface. The presence of this interface on the script indicates to the infrastructure that it is debuggable. 

While the IDataModelScriptDebug interface is the starting point to get access to the debug capabilities of a script provider, it is joined by a set of other interfaces in providing overall debug capabilities.

IDataModelScriptDebug

[IDataModelScriptDebugClient](nn-dbgmodel-idatamodelscriptdebugclient.md)

[IDataModelScriptDebugStack](nn-dbgmodel-idatamodelscriptdebugstack.md)

[IDataModelScriptDebugStackFrame](nn-dbgmodel-idatamodelscriptdebugstackframe.md)

[IDataModelScriptDebugVariableSetEnumerator](nn-dbgmodel-idatamodelscriptdebugvariablesetenumerator.md)

[IDataModelScriptDebugBreakpoint](nn-dbgmodel-idatamodelscriptdebugbreakpoint.md)

[IDataModelScriptDebugBreakpointEnumerator](nn-dbgmodel-idatamodelscriptdebugbreakpointenumerator.md)

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)
