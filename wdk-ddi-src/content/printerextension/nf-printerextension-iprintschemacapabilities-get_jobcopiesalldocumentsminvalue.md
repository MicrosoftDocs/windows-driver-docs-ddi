---
UID: NF:printerextension.IPrintSchemaCapabilities.get_JobCopiesAllDocumentsMinValue
title: IPrintSchemaCapabilities::get_JobCopiesAllDocumentsMinValue (printerextension.h)
description: Gets the JobCopiesAllDocuments parameter minimum value.
tech.root: print
ms.date: 08/01/2022
keywords: ["IPrintSchemaCapabilities::get_JobCopiesAllDocumentsMinValue"]
ms.keywords: IPrintSchemaCapabilities interface [Print Devices],JobCopiesAllDocumentsMinValue property, IPrintSchemaCapabilities.JobCopiesAllDocumentsMinValue, IPrintSchemaCapabilities.get_JobCopiesAllDocumentsMinValue, IPrintSchemaCapabilities::JobCopiesAllDocumentsMinValue, IPrintSchemaCapabilities::get_JobCopiesAllDocumentsMinValue, JobCopiesAllDocumentsMinValue property [Print Devices], JobCopiesAllDocumentsMinValue property [Print Devices],IPrintSchemaCapabilities interface, get_JobCopiesAllDocumentsMinValue, print.iprintschemacapabilities_jobcopiesalldocumentsminvalue, printerextension/IPrintSchemaCapabilities::JobCopiesAllDocumentsMinValue, printerextension/IPrintSchemaCapabilities::get_JobCopiesAllDocumentsMinValue
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
 - IPrintSchemaCapabilities::get_JobCopiesAllDocumentsMinValue
 - printerextension/IPrintSchemaCapabilities::get_JobCopiesAllDocumentsMinValue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaCapabilities::get_JobCopiesAllDocumentsMinValue
---

## -description

Gets the JobCopiesAllDocuments minimum value.

This property is read-only.

## -parameters

### -param pulJobCopiesAllDocumentsMinValue

This is the copy count minimum.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -see-also

[IPrintSchemaCapabilities](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemacapabilities)
