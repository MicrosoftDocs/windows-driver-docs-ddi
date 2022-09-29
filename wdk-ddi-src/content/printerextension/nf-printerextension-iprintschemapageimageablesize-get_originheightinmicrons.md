---
UID: NF:printerextension.IPrintSchemaPageImageableSize.get_OriginHeightInMicrons
title: IPrintSchemaPageImageableSize::get_OriginHeightInMicrons (printerextension.h)
description: Gets the vertical origin of the imageable area relative to the application media size.
tech.root: print
ms.date: 08/03/2022
keywords: ["IPrintSchemaPageImageableSize::get_OriginHeightInMicrons"]
ms.keywords: IPrintSchemaPageImageableSize interface [Print Devices],OriginHeightInMicrons property, IPrintSchemaPageImageableSize.OriginHeightInMicrons, IPrintSchemaPageImageableSize.get_OriginHeightInMicrons, IPrintSchemaPageImageableSize::OriginHeightInMicrons, IPrintSchemaPageImageableSize::get_OriginHeightInMicrons, OriginHeightInMicrons property [Print Devices], OriginHeightInMicrons property [Print Devices],IPrintSchemaPageImageableSize interface, get_OriginHeightInMicrons, print.iprintschemapageimageablesize_originheightinmicrons, printerextension/IPrintSchemaPageImageableSize::OriginHeightInMicrons, printerextension/IPrintSchemaPageImageableSize::get_OriginHeightInMicrons
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
 - IPrintSchemaPageImageableSize::get_OriginHeightInMicrons
 - printerextension/IPrintSchemaPageImageableSize::get_OriginHeightInMicrons
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaPageImageableSize::get_OriginHeightInMicrons
---

## -description

Gets the vertical origin of the imageable area relative to the application media size.

This property is read-only.

## -parameters

### -param pulOriginHeight

Defines the **ULONG** parameter *pulOriginHeight*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -see-also

[IPrintSchemaPageImageableSize](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemapageimageablesize)
