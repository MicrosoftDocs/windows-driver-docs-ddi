---
UID: NF:printerextension.IPrintJobCollection.get__NewEnum
title: IPrintJobCollection::get__NewEnum (printerextension.h)
description: Gets a pointer to the enumerants of IPrintJobCollection objects.
tech.root: print
ms.date: 08/03/2022
keywords: ["IPrintJobCollection::get__NewEnum"]
ms.keywords: IPrintJobCollection interface [Print Devices],NewEnum property, IPrintJobCollection.NewEnum, IPrintJobCollection.get__NewEnum, IPrintJobCollection::NewEnum, IPrintJobCollection::get_NewEnum, IPrintJobCollection::get__NewEnum, NewEnum property [Print Devices], NewEnum property [Print Devices],IPrintJobCollection interface, get__NewEnum, print.iprintjobcollection_newenum, printerextension/IPrintJobCollection::NewEnum, printerextension/IPrintJobCollection::get_NewEnum
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
ms.custom: RS5
f1_keywords:
 - IPrintJobCollection::get__NewEnum
 - printerextension/IPrintJobCollection::get__NewEnum
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintJobCollection::get__NewEnum
---

## -description

Gets a pointer to the enumerants of [IPrintJobCollection](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintjobcollection) objects.

This property is read-only.

## -parameters

### -param ppUnk

Defines the **IUnknown** parameter *ppUnk*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -see-also

[IPrintJobCollection](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintjobcollection)
