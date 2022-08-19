---
UID: NF:printerextension.IPrintSchemaOptionCollection.get_Count
title: IPrintSchemaOptionCollection::get_Count (printerextension.h)
description: Gets a count of the number of IPrintSchemaOption objects in the collection.
tech.root: print
ms.date: 08/03/2022
keywords: ["IPrintSchemaOptionCollection::get_Count"]
ms.keywords: Count property [Print Devices], Count property [Print Devices],IPrintSchemaOptionCollection interface, IPrintSchemaOptionCollection interface [Print Devices],Count property, IPrintSchemaOptionCollection.Count, IPrintSchemaOptionCollection.get_Count, IPrintSchemaOptionCollection::Count, IPrintSchemaOptionCollection::get_Count, get_Count, print.iprintschemaoptioncollection_count, printerextension/IPrintSchemaOptionCollection::Count, printerextension/IPrintSchemaOptionCollection::get_Count
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
req.typenames: 
f1_keywords:
 - IPrintSchemaOptionCollection::get_Count
 - printerextension/IPrintSchemaOptionCollection::get_Count
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaOptionCollection::get_Count
---

## -description

Gets a count of the number of [IPrintSchemaOption](./nn-printerextension-iprintschemaoption.md) objects in the collection.

This property is read-only.

## -parameters

### -param pulCount

Defines the **ULONG** parameter *pulCount*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -see-also

[IPrintSchemaOption](./nn-printerextension-iprintschemaoption.md)

[IPrintSchemaOptionCollection](./nn-printerextension-iprintschemaoptioncollection.md)