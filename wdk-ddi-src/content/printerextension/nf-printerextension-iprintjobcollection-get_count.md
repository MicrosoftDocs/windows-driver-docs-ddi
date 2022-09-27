---
UID: NF:printerextension.IPrintJobCollection.get_Count
title: IPrintJobCollection::get_Count (printerextension.h)
description: Gets the number of jobs in the print queue.
tech.root: print
ms.date: 07/29/2022
keywords: ["IPrintJobCollection::get_Count"]
ms.keywords: Count property [Print Devices], Count property [Print Devices],IPrintJobCollection interface, IPrintJobCollection interface [Print Devices],Count property, IPrintJobCollection.Count, IPrintJobCollection.get_Count, IPrintJobCollection::Count, IPrintJobCollection::get_Count, get_Count, print.iprintjobcollection_count, printerextension/IPrintJobCollection::Count, printerextension/IPrintJobCollection::get_Count
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
f1_keywords:
 - IPrintJobCollection::get_Count
 - printerextension/IPrintJobCollection::get_Count
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintJobCollection::get_Count
---

## -description

Gets the number of jobs in the print queue.

This property is read-only.

## -parameters

### -param pulCount

Defines the **ULONG** parameter *pulCount*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -see-also

[IPrintJobCollection](./nn-printerextension-iprintjobcollection.md)