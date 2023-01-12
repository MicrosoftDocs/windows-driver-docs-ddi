---
UID: NF:printerextension.IPrintJobCollection.GetAt
title: IPrintJobCollection::GetAt (printerextension.h)
description: Gets a pointer to an IPrintJob object.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrintJobCollection::GetAt"]
ms.keywords: GetAt, GetAt method [Print Devices], GetAt method [Print Devices],IPrintJobCollection interface, IPrintJobCollection interface [Print Devices],GetAt method, IPrintJobCollection.GetAt, IPrintJobCollection::GetAt, print.iprintjobcollection_getat, printerextension/IPrintJobCollection::GetAt
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
req.typenames: 
f1_keywords:
 - IPrintJobCollection::GetAt
 - printerextension/IPrintJobCollection::GetAt
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintJobCollection::GetAt
---

## -description

Gets a pointer to an [IPrintJob](./nn-printerextension-iprintjob.md) object.

## -parameters

### -param ulIndex [in]

Index of the **IPrintJob** object within the collection.

### -param ppJob [out, retval]

Pointer to an **IPrintJob** object.

## -returns

Returns an **HRESULT** value. If the method call was not successful, it returns the appropriate **HRESULT** error code.

## -see-also

[IPrintJob](./nn-printerextension-iprintjob.md)

[IPrintJobCollection](./nn-printerextension-iprintjobcollection.md)