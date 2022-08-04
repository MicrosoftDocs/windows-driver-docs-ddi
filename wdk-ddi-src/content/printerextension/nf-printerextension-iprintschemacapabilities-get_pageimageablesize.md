---
UID: NF:printerextension.IPrintSchemaCapabilities.get_PageImageableSize
title: IPrintSchemaCapabilities::get_PageImageableSize (printerextension.h)
description: Gets the imageable area information of the printer.
tech.root: print
ms.date: 08/01/2022
keywords: ["IPrintSchemaCapabilities::get_PageImageableSize"]
ms.keywords: IPrintSchemaCapabilities interface [Print Devices],PageImageableSize property, IPrintSchemaCapabilities.PageImageableSize, IPrintSchemaCapabilities.get_PageImageableSize, IPrintSchemaCapabilities::PageImageableSize, IPrintSchemaCapabilities::get_PageImageableSize, PageImageableSize property [Print Devices], PageImageableSize property [Print Devices],IPrintSchemaCapabilities interface, get_PageImageableSize, print.iprintschemacapabilities_pageimageablesize, printerextension/IPrintSchemaCapabilities::PageImageableSize, printerextension/IPrintSchemaCapabilities::get_PageImageableSize
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
 - IPrintSchemaCapabilities::get_PageImageableSize
 - printerextension/IPrintSchemaCapabilities::get_PageImageableSize
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaCapabilities::get_PageImageableSize
---

## -description

Gets the imageable area information of the printer.

This property is read-only.

## -parameters

### -param ppPageImageableSize

Defines the **IPrintSchemaPageImageableSize** parameter *ppPageImageableSize*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -see-also

[IPrintSchemaCapabilities](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemacapabilities)

[IPrintSchemaPageImageableSize](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemapageimageablesize)
