---
UID: NF:printerextension.IPrintSchemaPageImageableSize.get_ImageableSizeWidthInMicrons
title: IPrintSchemaPageImageableSize::get_ImageableSizeWidthInMicrons (printerextension.h)
description: Gets the horizontal dimension of the application media size relative to the page orientation.
tech.root: print
ms.date: 08/03/2022
keywords: ["IPrintSchemaPageImageableSize::get_ImageableSizeWidthInMicrons"]
ms.keywords: IPrintSchemaPageImageableSize interface [Print Devices],ImageableSizeWidthInMicrons property, IPrintSchemaPageImageableSize.ImageableSizeWidthInMicrons, IPrintSchemaPageImageableSize.get_ImageableSizeWidthInMicrons, IPrintSchemaPageImageableSize::ImageableSizeWidthInMicrons, IPrintSchemaPageImageableSize::get_ImageableSizeWidthInMicrons, ImageableSizeWidthInMicrons property [Print Devices], ImageableSizeWidthInMicrons property [Print Devices],IPrintSchemaPageImageableSize interface, get_ImageableSizeWidthInMicrons, print.iprintschemapageimageablesize_imageablesizewidthinmicrons, printerextension/IPrintSchemaPageImageableSize::ImageableSizeWidthInMicrons, printerextension/IPrintSchemaPageImageableSize::get_ImageableSizeWidthInMicrons
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
 - IPrintSchemaPageImageableSize::get_ImageableSizeWidthInMicrons
 - printerextension/IPrintSchemaPageImageableSize::get_ImageableSizeWidthInMicrons
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaPageImageableSize::get_ImageableSizeWidthInMicrons
---

## -description

Gets the horizontal dimension of the application media size relative to the page orientation.

This property is read-only.

## -parameters

### -param pulImageableSizeWidth

Defines the **ULONG** parameter *pulImageableSizeWidth*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -see-also

[IPrintSchemaPageImageableSize](./nn-printerextension-iprintschemapageimageablesize.md)