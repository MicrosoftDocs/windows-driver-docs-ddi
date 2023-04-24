---
UID: NF:printerextension.IPrinterExtensionContextCollection.get__NewEnum
title: IPrinterExtensionContextCollection::get__NewEnum method (printerextension.h)
description: Gets a pointer to the enumerants of IPrinterExtensionContextCollection objects
tech.root: print
ms.date: 07/29/2022
keywords: ["IPrinterExtensionContextCollection::get__NewEnum method"]
ms.keywords: IPrinterExtensionContextCollection, IPrinterExtensionContextCollection interface [Print Devices], NewEnum method, IPrinterExtensionContextCollection,get_NewEnum, NewEnum, IPrinterExtensionContextCollection::NewEnum, IPrinterExtensionContextCollection::get__NewEnum, NewEnum method [Print Devices], NewEnum method [Print Devices], IPrinterExtensionContextCollection interface, get__NewEnum,IPrinterExtensionContextCollection.get__NewEnum, print.iprinterextensioncontextcollection_newenum, printerextension/IPrinterExtensionContextCollection::NewEnum
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
f1_keywords:
 - IPrinterExtensionContextCollection::get__NewEnum
 - printerextension/IPrinterExtensionContextCollection::get__NewEnum
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterExtensionContextCollection::get__NewEnum
---

## -description

Gets a pointer to the enumerants of [IPrinterExtensionContextCollection](./nn-printerextension-iprinterextensioncontextcollection.md) objects.

## -parameters

### -param ppUnk [out, retval]

Defines the **IUnknown** parameter *ppUnk*.

## -returns

Returns an **HRESULT** value. If the property call was not successful,  it returns the appropriate **HRESULT** error code.

## -see-also

[IPrinterExtensionContextCollection](./nn-printerextension-iprinterextensioncontextcollection.md)