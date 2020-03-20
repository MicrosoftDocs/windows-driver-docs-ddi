---
UID: NN:dbgmodel.IDataModelScriptDebugClient
title: IDataModelScriptDebugClient (dbgmodel.h)
description: The client of the script debugger implements this interface as a part of a two-way communication channel with the script debugger.
ms.assetid: e6dbd395-a973-4447-a423-9d26ce13c90b
ms.date: 07/13/2018
keywords: ["IDataModelScriptDebugClient interface"]
f1_keywords:
 - "dbgmodel/IDataModelScriptDebugClient"
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
topic_type: 
- apiref
api_type: 
- COM
api_location: 
- dbgmodel.h
api_name: 
- IDataModelScriptDebugClient
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptDebugClient interface

## -description

The client of the script debugger implements this interface as a part of a two-way communication channel with the script debugger.

The user interface which wishes to provide the capability of script debugging implements the IDataModelScriptDebugClient interface. The script provider utilizes this interface to pass debug information back and forth (e.g.: events which occur, breakpoints, etc...)


## -inheritance
IDataModelScriptDebugClient interits from IUnknown. 
## -remarks

The debug host or debugger application which wishes to provide an interface around script debugging must provide an implementation of the IDataModelScriptDebugClient interface to the script debugger via the StartDebugging method on the debug interface for the script. 

The IDataModelScriptDebugClient is the communication channel across which debug events are passed and control goes from the script execution engine to a debugger interface. 


## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
