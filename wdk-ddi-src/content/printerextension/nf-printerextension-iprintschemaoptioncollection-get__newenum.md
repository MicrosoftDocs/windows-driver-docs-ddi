---
UID: NF:printerextension.IPrintSchemaOptionCollection.get__NewEnum
tech.root: print
title: IPrintSchemaOptionCollection::get__NewEnum
ms.date: 10/06/2022
targetos: Windows
description: Learn more about the IPrintSchemaOptionCollection::NewEnum property.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: printerextension.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - printerextension.h
api_name:
 - IPrintSchemaOptionCollection::get__NewEnum
f1_keywords:
 - IPrintSchemaOptionCollection::get__NewEnum
 - printerextension/IPrintSchemaOptionCollection::get__NewEnum
dev_langs:
 - c++
helpviewer_keywords:
 - get__NewEnum
---

## -description

Gets a pointer to the enumerants of [**IPrintSchemaOptionCollection**](nn-printerextension-iprintschemaoptioncollection.md) objects.

This property is read-only.

## -parameters

### -param ppUnk

Pointer to object of type **IUnknown**.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -see-also

[**IPrintSchemaOptionCollection**](nn-printerextension-iprintschemaoptioncollection.md)
