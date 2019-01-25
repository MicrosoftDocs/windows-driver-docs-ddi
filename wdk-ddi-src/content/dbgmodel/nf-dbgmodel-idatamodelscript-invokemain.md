---
UID: NF:dbgmodel.IDataModelScript.InvokeMain
title: IDataModelScript::InvokeMain (dbgmodel.h)
description: If the script has a "main function" which is intended to execute from a UI invocation, it indicates such via a true return from the IsInvocable method.
ms.assetid: c2ade702-c9fb-478c-bca7-f92fdbd748e2
ms.date: 08/20/2018
ms.topic: method
ms.keywords: IDataModelScript::InvokeMain, InvokeMain, IDataModelScript.InvokeMain, IDataModelScript::InvokeMain, IDataModelScript.InvokeMain
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
-	IDataModelScript.InvokeMain
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScript::InvokeMain


## -description

If the script has a "main function" which is intended to execute from a UI invocation, it indicates such via a true return from the IsInvocable method. The user interface can then call the InvokeMain method to actually "invoke" the script. Note that this is distinct from *Execute* which runs all root code and bridges the script to the namespace of the underlying host. 

This method may fail with E_NOTIMPL if the script does not contain a "main function" or the provider does not define such. 

Note that an application which hosts the data model may load and execute a script once but call the InvokeMain method an arbitrary number of times without an intervening Execute call. It is expected that this would preserve the "script context", keep the script loaded, and just call a method within the script multiple times. 

If there are errors or other events which occur during execution of the script, such (and their location within the script) can be passed across the communication channel between the IDataModelScript and the inpassed IDataModelScriptClient. 


## -parameters

### -param client

An interface to the client which is requesting the main function be called. If there are errors or other events which occur during execution of the main function, the script can pass this information and its location within the script back to the client via method calls on this interface.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDataModelScript interface](nn-dbgmodel-idatamodelscript.md)
