---
UID: NF:dbgmodel.IDataModelScriptHostContext.NotifyScriptChange
title: IDataModelScriptHostContext::NotifyScriptChange
author: windows-driver-content
description: It is required that a script provider notify the debug host upon certain operations occurring with a method call to the NotifyScriptChange method on the associated context. 
ms.assetid: c30d734e-4360-4e87-82f9-cfda1b4b5476
ms.author: windowsdriverdev
ms.date: 09/10/2018
ms.topic: method
ms.keywords: IDataModelScriptHostContext::NotifyScriptChange, NotifyScriptChange, IDataModelScriptHostContext.NotifyScriptChange, IDataModelScriptHostContext::NotifyScriptChange, IDataModelScriptHostContext.NotifyScriptChange
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
-	IDataModelScriptHostContext.NotifyScriptChange
product: Windows
targetos: Windows
tech.root: debugger
---

# IDataModelScriptHostContext::NotifyScriptChange


## -description

It is required that a script provider notify the debug host upon certain operations occurring with a method call to the NotifyScriptChange method on the associated context. Such operations are defined as members of the ScriptChangeKind enumeration which is defined as follows: 

Enumerant	| Description
|-------|--------|
ScriptRename	| Indicates that the name of the script has changed. This notification should be made during a Rename call on the IDataModelScript. The host may then query back the name of the script via a GetName method. The placement of the context namespace (as returned by GetNamespaceObject) may completely change as a result of this notification.


## -parameters

### -param script
The script for which the notification is occurring.

### -param changeKind
The nature of the notification.


## -returns
This method returns HRESULT which indicates success or failure.
## -remarks

## -see-also
[IDataModelScriptHostContext interface](nn-dbgmodel-idatamodelscripthostcontext.md)
