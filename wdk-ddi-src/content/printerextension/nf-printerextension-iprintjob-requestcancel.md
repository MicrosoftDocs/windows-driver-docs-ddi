---
UID: NF:printerextension.IPrintJob.RequestCancel
title: IPrintJob::RequestCancel (printerextension.h)
description: Requests the cancellation of a print job.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrintJob::RequestCancel"]
ms.keywords: IPrintJob interface [Print Devices],RequestCancel method, IPrintJob.RequestCancel, IPrintJob::RequestCancel, RequestCancel, RequestCancel method [Print Devices], RequestCancel method [Print Devices],IPrintJob interface, print.iprintjob_requestcancel, printerextension/IPrintJob::RequestCancel
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
 - IPrintJob::RequestCancel
 - printerextension/IPrintJob::RequestCancel
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintJob::RequestCancel
---

## -description

Requests the cancellation of a print job.

## -returns

Returns an **HRESULT** value. If the method call was not successful, it returns the appropriate **HRESULT** error code.

## -remarks

The **RequestCancel** method does not wait for the cancellation of a print job to be processed to completion before it returns.

## -see-also

[IPrintJob](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintjob)
