---
UID: NF:printerextension.IPrintSchemaPageImageableSize.get_ImageableSizeHeightInMicrons
title: IPrintSchemaPageImageableSize::get_ImageableSizeHeightInMicrons (printerextension.h)
description: Gets the vertical dimension of the application media size relative to the page orientation.
tech.root: print
ms.date: 08/03/2022
keywords: ["IPrintSchemaPageImageableSize::get_ImageableSizeHeightInMicrons"]
ms.keywords: IPrintSchemaPageImageableSize interface [Print Devices],ImageableSizeHeightInMicrons property, IPrintSchemaPageImageableSize.ImageableSizeHeightInMicrons, IPrintSchemaPageImageableSize.get_ImageableSizeHeightInMicrons, IPrintSchemaPageImageableSize::ImageableSizeHeightInMicrons, IPrintSchemaPageImageableSize::get_ImageableSizeHeightInMicrons, ImageableSizeHeightInMicrons property [Print Devices], ImageableSizeHeightInMicrons property [Print Devices],IPrintSchemaPageImageableSize interface, get_ImageableSizeHeightInMicrons, print.iprintschemapageimageablesize_imageablesizeheightinmicrons, printerextension/IPrintSchemaPageImageableSize::ImageableSizeHeightInMicrons, printerextension/IPrintSchemaPageImageableSize::get_ImageableSizeHeightInMicrons
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
 - IPrintSchemaPageImageableSize::get_ImageableSizeHeightInMicrons
 - printerextension/IPrintSchemaPageImageableSize::get_ImageableSizeHeightInMicrons
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaPageImageableSize::get_ImageableSizeHeightInMicrons
---

## -description

Gets the vertical dimension of the application media size relative to the page orientation.

This property is read-only.

## -parameters

### -param pulImageableSizeHeight

Defines the **ULONG** parameter *pulImageableSizeHeight*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -see-also

[IPrintSchemaPageImageableSize](./nn-printerextension-iprintschemapageimageablesize.md)