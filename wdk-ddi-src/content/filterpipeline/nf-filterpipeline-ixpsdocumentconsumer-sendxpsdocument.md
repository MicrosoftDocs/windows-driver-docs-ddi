---
UID: NF:filterpipeline.IXpsDocumentConsumer.SendXpsDocument
title: IXpsDocumentConsumer::SendXpsDocument (filterpipeline.h)
description: The SendXpsDocument method sends an XPS document to the pipeline.
old-location: print\ixpsdocumentconsumer_sendxpsdocument.htm
tech.root: print
ms.assetid: ad9f0f6b-19a6-4c99-9350-7ca249cf4774
ms.date: 04/20/2018
keywords: ["IXpsDocumentConsumer::SendXpsDocument"]
ms.keywords: IXpsDocumentConsumer interface [Print Devices],SendXpsDocument method, IXpsDocumentConsumer.SendXpsDocument, IXpsDocumentConsumer::SendXpsDocument, SendXpsDocument, SendXpsDocument method [Print Devices], SendXpsDocument method [Print Devices],IXpsDocumentConsumer interface, filterpipeline/IXpsDocumentConsumer::SendXpsDocument, filterpipeline_f8816c77-a8d0-4d44-bd12-adaf9194c34c.xml, print.ixpsdocumentconsumer_sendxpsdocument
req.header: filterpipeline.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Filterpipeline.idl
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
 - IXpsDocumentConsumer::SendXpsDocument
 - filterpipeline/IXpsDocumentConsumer::SendXpsDocument
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - filterpipeline.h
api_name:
 - IXpsDocumentConsumer.SendXpsDocument
---

# IXpsDocumentConsumer::SendXpsDocument


## -description

The <code>SendXpsDocument</code> method sends an XPS document to the pipeline.

## -parameters

### -param pIXpsDocument 

[in]
A pointer to the XPS document object to send.

## -returns

<code>SendXpsDocument</code> returns an <b>HRESULT</b> value.

## -remarks

The <a href="/windows-hardware/drivers/ddi/filterpipeline/nn-filterpipeline-ixpsdocument">IXpsDocument</a> interface is the root for a tree view of an XPS document. The tree also contains one fixed document sequence and any number of fixed documents and fixed pages.

Only one XpsDocument interface can be sent. The <code>SendXpsDocument</code> method will fail if a filter submits more than one XpsDocument interface for the same print job.

## -see-also

<a href="/windows-hardware/drivers/ddi/filterpipeline/nn-filterpipeline-ixpsdocument">IXpsDocument</a>



<a href="/windows-hardware/drivers/ddi/filterpipeline/nn-filterpipeline-ixpsdocumentconsumer">IXpsDocumentConsumer</a>