---
UID: NF:printerextension.IPrintSchemaPageImageableSize.get_ExtentWidthInMicrons
title: IPrintSchemaPageImageableSize::get_ExtentWidthInMicrons (printerextension.h)
description: Gets the horizontal distance between the origin and the bounding limit of the application media size.
tech.root: print
ms.date: 08/03/2022
keywords: ["IPrintSchemaPageImageableSize::get_ExtentWidthInMicrons"]
ms.keywords: ExtentWidthInMicrons property [Print Devices], ExtentWidthInMicrons property [Print Devices],IPrintSchemaPageImageableSize interface, IPrintSchemaPageImageableSize interface [Print Devices],ExtentWidthInMicrons property, IPrintSchemaPageImageableSize.ExtentWidthInMicrons, IPrintSchemaPageImageableSize.get_ExtentWidthInMicrons, IPrintSchemaPageImageableSize::ExtentWidthInMicrons, IPrintSchemaPageImageableSize::get_ExtentWidthInMicrons, get_ExtentWidthInMicrons, print.iprintschemapageimageablesize_extentwidthinmicrons, printerextension/IPrintSchemaPageImageableSize::ExtentWidthInMicrons, printerextension/IPrintSchemaPageImageableSize::get_ExtentWidthInMicrons
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
 - IPrintSchemaPageImageableSize::get_ExtentWidthInMicrons
 - printerextension/IPrintSchemaPageImageableSize::get_ExtentWidthInMicrons
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaPageImageableSize::get_ExtentWidthInMicrons
---

## -description

Gets the horizontal distance between the origin and the bounding limit of the application media size.

This property is read-only.

## -parameters

### -param pulExtentWidth

Defines the **ULONG** parameter *pulExtentWidth*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -see-also

[IPrintSchemaPageImageableSize](./nn-printerextension-iprintschemapageimageablesize.md)