---
UID: NF:dbgeng.IDebugSymbols3.IsManagedModule
title: IDebugSymbols3::IsManagedModule (dbgeng.h)
description: Checks whether the engine is using managed debugging support when it retrieves information for a module.
old-location: debugger\idebugsymbols3_ismanagedmodule.htm
tech.root: debugger
ms.assetid: AECBA6E8-B030-4418-A561-9E48B4880D15
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::IsManagedModule"]
ms.keywords: IDebugSymbols3 interface [Windows Debugging],IsManagedModule method, IDebugSymbols3.IsManagedModule, IDebugSymbols3::IsManagedModule, IsManagedModule, IsManagedModule method [Windows Debugging], IsManagedModule method [Windows Debugging],IDebugSymbols3 interface, dbgeng/IDebugSymbols3::IsManagedModule, debugger.idebugsymbols3_ismanagedmodule
f1_keywords:
 - "dbgeng/IDebugSymbols3.IsManagedModule"
 - "IDebugSymbols3.IsManagedModule"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Dbgeng.h
api_name:
- IDebugSymbols3.IsManagedModule
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::IsManagedModule


## -description


Checks whether the engine is using managed
    debugging support when it retrieves information
    for a module.


## -parameters




### -param Index 
[in]
The index of a module.


### -param Base 
[in]
The base of the module.


## -returns



<b>IDebugSymbols3::IsManagedModule</b> returns a value of <b>S_OK</b> if the engine is using managed
    debugging support when it retrieves information
    for a module.




## -remarks



It can be expensive to run this check.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>
 

 

