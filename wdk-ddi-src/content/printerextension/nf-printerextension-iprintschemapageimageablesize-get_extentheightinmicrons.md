---
UID: NF:printerextension.IPrintSchemaPageImageableSize.get_ExtentHeightInMicrons
title: IPrintSchemaPageImageableSize::get_ExtentHeightInMicrons (printerextension.h)
description: Gets the vertical distance between the origin and the bounding limit of the canvas application media size.
tech.root: print
ms.date: 08/03/2022
keywords: ["IPrintSchemaPageImageableSize::get_ExtentHeightInMicrons"]
ms.keywords: ExtentHeightInMicrons property [Print Devices], ExtentHeightInMicrons property [Print Devices],IPrintSchemaPageImageableSize interface, IPrintSchemaPageImageableSize interface [Print Devices],ExtentHeightInMicrons property, IPrintSchemaPageImageableSize.ExtentHeightInMicrons, IPrintSchemaPageImageableSize.get_ExtentHeightInMicrons, IPrintSchemaPageImageableSize::ExtentHeightInMicrons, IPrintSchemaPageImageableSize::get_ExtentHeightInMicrons, get_ExtentHeightInMicrons, print.iprintschemapageimageablesize_extentheightinmicrons, printerextension/IPrintSchemaPageImageableSize::ExtentHeightInMicrons, printerextension/IPrintSchemaPageImageableSize::get_ExtentHeightInMicrons
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
 - IPrintSchemaPageImageableSize::get_ExtentHeightInMicrons
 - printerextension/IPrintSchemaPageImageableSize::get_ExtentHeightInMicrons
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaPageImageableSize::get_ExtentHeightInMicrons
---

## -description

Gets the vertical distance between the origin and the bounding limit of the canvas application media size.

This property is read-only.

## -parameters

### -param pulExtentHeight

Defines the ULONG parameter *pulExtentHeight*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -see-also

[IPrintSchemaPageImageableSize](./nn-printerextension-iprintschemapageimageablesize.md)