---
UID: NF:dbgmodel.IDataModelScriptTemplate.GetContent
title: IDataModelScriptTemplate::GetContent (dbgmodel.h)
description: The GetContent method returns the content (or code) of the template.
ms.date: 08/21/2018
keywords: ["IDataModelScriptTemplate::GetContent"]
ms.keywords: IDataModelScriptTemplate::GetContent, GetContent, IDataModelScriptTemplate.GetContent, IDataModelScriptTemplate::GetContent, IDataModelScriptTemplate.GetContent
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
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IDataModelScriptTemplate::GetContent
 - dbgmodel/IDataModelScriptTemplate::GetContent
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelScriptTemplate.GetContent
---

# IDataModelScriptTemplate::GetContent


## -description

The GetContent method returns the content (or code) of the template. This is what would be pre-filled into the edit window if a user elected to create a new script from this template. The template is responsible for creating (and returning) a standard stream over the content that the client can pull.

## -parameters

### -param contentStream

A newly created standard stream over the content (code) for the template. This stream may be backed by memory, a file, or whatever the implementation wishes.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDataModelScriptTemplate interface](nn-dbgmodel-idatamodelscripttemplate.md)

