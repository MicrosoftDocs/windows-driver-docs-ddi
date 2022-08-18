---
UID: NF:printerextension.IPrintSchemaTicket.get_JobCopiesAllDocuments
title: IPrintSchemaTicket::get_JobCopiesAllDocuments (printerextension.h)
description: Gets the copy count.
tech.root: print
ms.date: 08/03/2022
keywords: ["IPrintSchemaTicket::get_JobCopiesAllDocuments"]
ms.keywords: IPrintSchemaTicket interface [Print Devices],JobCopiesAllDocuments property, IPrintSchemaTicket.JobCopiesAllDocuments, IPrintSchemaTicket.get_JobCopiesAllDocuments, IPrintSchemaTicket::JobCopiesAllDocuments, IPrintSchemaTicket::get_JobCopiesAllDocuments, JobCopiesAllDocuments property [Print Devices], JobCopiesAllDocuments property [Print Devices],IPrintSchemaTicket interface, get_JobCopiesAllDocuments, print.iprintschematicket_jobcopiesalldocuments, printerextension/IPrintSchemaTicket::JobCopiesAllDocuments, printerextension/IPrintSchemaTicket::get_JobCopiesAllDocuments
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
 - IPrintSchemaTicket::get_JobCopiesAllDocuments
 - printerextension/IPrintSchemaTicket::get_JobCopiesAllDocuments
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaTicket::get_JobCopiesAllDocuments
---

## -description

Gets the copy count.

This property is read-only.

## -parameters

### -param pulJobCopiesAllDocuments

Defines the **ULONG** parameter *pulJobCopiesAllDocuments*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -see-also

[IPrintSchemaTicket](./nn-printerextension-iprintschematicket.md)