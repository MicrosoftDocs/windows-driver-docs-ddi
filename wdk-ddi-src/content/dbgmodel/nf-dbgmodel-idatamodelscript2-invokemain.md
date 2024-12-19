---
UID: NF:dbgmodel.IDataModelScript2.InvokeMain
tech.root: debugger
title: IDataModelScript2::InvokeMain
ms.date: 12/16/2024
targetos: Windows
description: If the script has a "main function" which is intended to execute from a UI invocation, it indicates such via a true return from the IsInvocable method.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dbgmodel.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelScript2::InvokeMain
f1_keywords:
 - IDataModelScript2::InvokeMain
 - dbgmodel/IDataModelScript2::InvokeMain
dev_langs:
 - c++
helpviewer_keywords:
 - InvokeMain
---

## -description

If the script has a "main function" which is intended to execute from a UI invocation, it indicates such via a true return from the IsInvocable method. The user interface can then call the InvokeMain method to actually "invoke" the script. Note that this is distinct from *Execute* which runs all root code and bridges the script to the namespace of the underlying host. 

This method may fail with E_NOTIMPL if the script does not contain a "main function" or the provider does not define such. 

Note that an application which hosts the data model may load and execute a script once but call the InvokeMain method an arbitrary number of times without an intervening Execute call. It is expected that this would preserve the "script context", keep the script loaded, and just call a method within the script multiple times. 

If there are errors or other events which occur during execution of the script, such (and their location within the script) can be passed across the communication channel between the [IDataModelScript2](nn-dbgmodel-idatamodelscript2.md) and the inpassed [IDataModelScriptClient](nn-dbgmodel-idatamodelscriptclient.md).

## -parameters

### -param client

An interface to the client which is requesting the main function be called. If there are errors or other events which occur during execution of the main function, the script can pass this information and its location within the script back to the client via method calls on this interface.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDataModelScript2 interface](nn-dbgmodel-idatamodelscript2.md)