---
UID: NF:dbgmodel.IDebugHostBaseClass.GetName
title: IDebugHostBaseClass::GetName
author: windows-driver-content
description: TBD
ms.assetid: 55bee20c-7b4f-42ae-97e5-4aa4e24b22b4
ms.author: windowsdriverdev
ms.date: 08/14/2018
ms.topic: method
ms.keywords: IDebugHostBaseClass::GetName, GetName, IDebugHostBaseClass.GetName, IDebugHostBaseClass::GetName, IDebugHostBaseClass.GetName
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
-	IDebugHostBaseClass.GetName
product: Windows
targetos: Windows
tech.root: debugger
---

# IDebugHostBaseClass::GetName


## -description

Returns the name of the symbol if the symbol has a name.  If the symbol does not have a name, an error is returned.


## -parameters

### -param symbolName
The name of the symbol will be returned here as a string allocated via the SysAllocString method.  The caller is responsible for freeing the allocated string via the SysFreeString method.

## -returns
This method returns HRESULT that indicates success or failure.

## -see-also

[IDebugHostBaseClass interface](nn-dbgmodel-idebughostbaseclass.md)
