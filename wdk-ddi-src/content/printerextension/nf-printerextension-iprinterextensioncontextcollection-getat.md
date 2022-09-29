---
UID: NF:printerextension.IPrinterExtensionContextCollection.GetAt
title: IPrinterExtensionContextCollection::GetAt (printerextension.h)
description: Gets a pointer to an IPrinterExtensionContext object.
tech.root: print
ms.date: 08/03/2022
keywords: ["IPrinterExtensionContextCollection::GetAt"]
ms.keywords: GetAt, GetAt method [Print Devices], GetAt method [Print Devices],IPrinterExtensionContextCollection interface, IPrinterExtensionContextCollection interface [Print Devices],GetAt method, IPrinterExtensionContextCollection.GetAt, IPrinterExtensionContextCollection::GetAt, get_GetAt, print.iprinterextensioncontextcollection_getat, printerextension/IPrinterExtensionContextCollection::GetAt
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
 - IPrinterExtensionContextCollection::GetAt
 - printerextension/IPrinterExtensionContextCollection::GetAt
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterExtensionContextCollection::GetAt
---

## -description

Gets a pointer to an [IPrinterExtensionContext](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterextensioncontext) object.

## -parameters

### -param ulIndex [in]

The index of the [IPrinterExtensionContext](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterextensioncontext) object within the collection.

### -param ppContext [out, retval]

Pointer to an [IPrinterExtensionContext](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterextensioncontext) interface.

## -returns

This method returns an **HRESULT** value.

## -see-also

[IPrinterExtensionContext](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterextensioncontext)

[IPrinterExtensionContextCollection](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterextensioncontextcollection)
