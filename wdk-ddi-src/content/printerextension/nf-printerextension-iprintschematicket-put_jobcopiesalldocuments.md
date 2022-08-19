---
UID: NF:printerextension.IPrintSchemaTicket.put_JobCopiesAllDocuments
title: IPrintSchemaTicket::put_JobCopiesAllDocuments (printerextension.h)
description: Sets the copy count.
tech.root: print
ms.date: 08/03/2022
keywords: ["IPrintSchemaTicket::put_JobCopiesAllDocuments"]
ms.keywords: IPrintSchemaTicket, IPrintSchemaTicket interface [Print Devices],JobCopiesAllDocuments property, IPrintSchemaTicket.JobCopiesAllDocuments, IPrintSchemaTicket.put_JobCopiesAllDocuments, IPrintSchemaTicket::JobCopiesAllDocuments, IPrintSchemaTicket::put_JobCopiesAllDocuments, JobCopiesAllDocuments property [Print Devices], JobCopiesAllDocuments property [Print Devices],IPrintSchemaTicket interface, print.iprintschematicket_put_jobcopiesalldocuments, printerextension/IPrintSchemaTicket::JobCopiesAllDocuments, printerextension/IPrintSchemaTicket::put_JobCopiesAllDocuments, put_JobCopiesAllDocuments
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
 - IPrintSchemaTicket::put_JobCopiesAllDocuments
 - printerextension/IPrintSchemaTicket::put_JobCopiesAllDocuments
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaTicket::put_JobCopiesAllDocuments
---

## -description

Sets the copy count.

This property is write-only.

## -parameters

### -param ulJobCopiesAllDocuments

Defines the **ULONG** parameter *ulJobCopiesAllDocuments*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -remarks

Be aware of the fact that the [IPrintSchemaTicket::GetCapabilities](./nf-printerextension-iprintschematicket-getcapabilities.md)  method retrieves a new PrintCapabilities document, which it also caches every time it is invoked. This means that if you use **IPrintSchemaTicket::put_JobCopiesAllDocuments** or [IPrintSchemaFeature::SelectedOption](./nf-printerextension-iprintschemafeature-put_selectedoption.md) on PrintTicket, the cached PrintCapabilities document gets corrupted or modified and the cache will be purged.

## -see-also

[IPrintSchemaFeature::SelectedOption](./nf-printerextension-iprintschemafeature-put_selectedoption.md)

[IPrintSchemaTicket](./nn-printerextension-iprintschematicket.md)

[IPrintSchemaTicket::GetCapabilities](./nf-printerextension-iprintschematicket-getcapabilities.md)