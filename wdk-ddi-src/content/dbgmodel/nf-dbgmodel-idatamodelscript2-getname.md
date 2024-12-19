---
UID: NF:dbgmodel.IDataModelScript2.GetName
tech.root: debugger
title: IDataModelScript2::GetName
ms.date: 12/16/2024
targetos: Windows
description: The GetName method returns the name of the script as an allocated string via the SysAllocString function.
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
 - IDataModelScript2::GetName
f1_keywords:
 - IDataModelScript2::GetName
 - dbgmodel/IDataModelScript2::GetName
dev_langs:
 - c++
helpviewer_keywords:
 - GetName
---

## -description

The GetName method returns the name of the script as an allocated string via the SysAllocString function. If the script does not yet have a name, the method should return a null BSTR. It should not fail in this circumstance. If the script is explicitly renamed via a call to the Rename method, the GetName method should return the newly assigned name.

## -parameters

### -param scriptName

The name of the script should be returned here as a string allocated via SysAllocString. The caller is responsible for freeing this string via the SysFreeString method. Note that if the script is unnamed, the method should return a null BSTR as the output. It should still succeed in this case.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDataModelScript2 interface](nn-dbgmodel-idatamodelscript2.md)