---
UID: NF:dbgmodel.IDataModelScriptTemplateEnumerator.GetNext
title: IDataModelScriptTemplateEnumerator::GetNext
author: windows-driver-content
description: TBD
ms.assetid: 0e713d20-12a1-457e-9638-03064773c19f
ms.author: windowsdriverdev
ms.date: 08/21/2018
ms.topic: method
ms.keywords: IDataModelScriptTemplateEnumerator::GetNext, GetNext, IDataModelScriptTemplateEnumerator.GetNext, IDataModelScriptTemplateEnumerator::GetNext, IDataModelScriptTemplateEnumerator.GetNext
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
-	IDataModelScriptTemplateEnumerator.GetNext
product: Windows
targetos: Windows
tech.root: debugger
---

# IDataModelScriptTemplateEnumerator::GetNext


## -description

The GetNext method moves the enumerator to the next template and returns it. At the end of enumeration, the enumerator returns E_BOUNDS. Once the E_BOUNDS marker has been hit, the enumerator will continue to produce E_BOUNDS errors indefinitely until a Reset call is made. 

## -parameters

### -param templateContent

The next template in enumeration order is returned here as a component implementing the IDataModelScriptTemplate interface.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDataModelScriptTemplateEnumerator interface](nn-dbgmodel-idatamodelscripttemplateenumerator.md)
