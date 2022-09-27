---
UID: NF:printerextension.IPrintJob.get_Id
title: IPrintJob::get_Id (printerextension.h)
description: Gets the print job identifier (ID).
tech.root: print
ms.date: 07/29/2022
keywords: ["IPrintJob::get_Id"]
ms.keywords: IPrintJob interface [Print Devices],Id property, IPrintJob.Id, IPrintJob.get_Id, IPrintJob::Id, IPrintJob::get_Id, Id property [Print Devices], Id property [Print Devices],IPrintJob interface, get_Id, print.iprintjob_id, printerextension/IPrintJob::Id, printerextension/IPrintJob::get_Id
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
 - IPrintJob::get_Id
 - printerextension/IPrintJob::get_Id
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintJob::get_Id
---

## -description

Gets the print job identifier (ID).

This property is read-only.

## -parameters

### -param pulID

Defines the **ULONG** parameter *pulID*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -remarks

You must not use the **IPrintJob::Id** property to invoke spooler Job APIs. This property is only provided as a way for you to identify a particular job, and to help with ordering or sorting of the jobs in the job snapshot.

## -see-also

[IPrintJob](./nn-printerextension-iprintjob.md)