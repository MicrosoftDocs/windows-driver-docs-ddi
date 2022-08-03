---
UID: NF:printerextension.IPrintSchemaPageImageableSize.get_OriginWidthInMicrons
title: IPrintSchemaPageImageableSize::get_OriginWidthInMicrons (printerextension.h)
description: Gets the horizontal origin of the imageable area relative to the application media size.
tech.root: print
ms.date: 08/03/2022
keywords: ["IPrintSchemaPageImageableSize::get_OriginWidthInMicrons"]
ms.keywords: IPrintSchemaPageImageableSize interface [Print Devices],OriginWidthInMicrons property, IPrintSchemaPageImageableSize.OriginWidthInMicrons, IPrintSchemaPageImageableSize.get_OriginWidthInMicrons, IPrintSchemaPageImageableSize::OriginWidthInMicrons, IPrintSchemaPageImageableSize::get_OriginWidthInMicrons, OriginWidthInMicrons property [Print Devices], OriginWidthInMicrons property [Print Devices],IPrintSchemaPageImageableSize interface, get_OriginWidthInMicrons, print.iprintschemapageimageablesize_originwidthinmicrons, printerextension/IPrintSchemaPageImageableSize::OriginWidthInMicrons, printerextension/IPrintSchemaPageImageableSize::get_OriginWidthInMicrons
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
 - IPrintSchemaPageImageableSize::get_OriginWidthInMicrons
 - printerextension/IPrintSchemaPageImageableSize::get_OriginWidthInMicrons
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaPageImageableSize::get_OriginWidthInMicrons
---

## -description

Gets the horizontal origin of the imageable area relative to the application media size.

This property is read-only.

## -parameters

### -param pulOriginWidth

Defines the **ULONG** parameter *pulOriginWidth*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -see-also

[IPrintSchemaPageImageableSize](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemapageimageablesize)
