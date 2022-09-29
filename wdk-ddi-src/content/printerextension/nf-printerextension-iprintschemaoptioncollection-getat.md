---
UID: NF:printerextension.IPrintSchemaOptionCollection.GetAt
title: IPrintSchemaOptionCollection::GetAt (printerextension.h)
description: Gets a pointer to an IPrintSchemaOption object.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrintSchemaOptionCollection::GetAt"]
ms.keywords: GetAt, GetAt method [Print Devices], GetAt method [Print Devices],IPrintSchemaOptionCollection interface, IPrintSchemaOptionCollection interface [Print Devices],GetAt method, IPrintSchemaOptionCollection.GetAt, IPrintSchemaOptionCollection::GetAt, print.iprintschemaoptioncollection_getat, printerextension/IPrintSchemaOptionCollection::GetAt
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
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
req.typenames: 
f1_keywords:
 - IPrintSchemaOptionCollection::GetAt
 - printerextension/IPrintSchemaOptionCollection::GetAt
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaOptionCollection::GetAt
---

## -description

Gets a pointer to an [IPrintSchemaOption](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaoption) object.

## -parameters

### -param ulIndex [in]

Index of the **IPrintSchemaOption** object within the collection.

### -param ppOption [out, retval, optional]

Pointer to an [IPrintSchemaOption](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaoption) object.

## -returns

Returns an **HRESULT** value. If the method call was not successful,  it returns the appropriate **HRESULT** error code.

## -see-also

[IPrintSchemaOption](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaoption)

[IPrintSchemaOptionCollection](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaoptioncollection)
