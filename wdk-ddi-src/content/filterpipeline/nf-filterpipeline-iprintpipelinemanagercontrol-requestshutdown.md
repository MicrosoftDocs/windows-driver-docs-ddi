---
UID: NF:filterpipeline.IPrintPipelineManagerControl.RequestShutdown
title: IPrintPipelineManagerControl::RequestShutdown (filterpipeline.h)
description: The RequestShutdown method requests that a pipeline be shut down.
old-location: print\iprintpipelinemanagercontrol_requestshutdown.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IPrintPipelineManagerControl::RequestShutdown"]
ms.keywords: IPrintPipelineManagerControl interface [Print Devices],RequestShutdown method, IPrintPipelineManagerControl.RequestShutdown, IPrintPipelineManagerControl::RequestShutdown, RequestShutdown, RequestShutdown method [Print Devices], RequestShutdown method [Print Devices],IPrintPipelineManagerControl interface, filterpipeline/IPrintPipelineManagerControl::RequestShutdown, filterpipeline_b16337ab-92e1-4e5e-be84-bddf89bff0a1.xml, print.iprintpipelinemanagercontrol_requestshutdown
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
 - IPrintPipelineManagerControl::RequestShutdown
 - filterpipeline/IPrintPipelineManagerControl::RequestShutdown
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - filterpipeline.h
api_name:
 - IPrintPipelineManagerControl::RequestShutdown
---

# IPrintPipelineManagerControl::RequestShutdown


## -description

The <code>RequestShutdown</code> method requests that a pipeline be shut down.

## -parameters

### -param hrReason 

[in]
An <b>HRESULT</b> value that indicates the reason for the lack of memory.

### -param pReason 

[in]
Not used. Set to <b>NULL</b>.

## -returns

<code>RequestShutdown</code> returns an <b>HRESULT</b> value.

## -remarks

A filter that uses the <a href="/windows-hardware/drivers/ddi/filterpipeline/nn-filterpipeline-ixpsdocumentconsumer">IXpsDocumentConsumer</a> interface must call <code>IPrintPipelineManagerControl::RequestShutdown</code> before it calls <a href="/windows-hardware/drivers/ddi/filterpipeline/nf-filterpipeline-ixpsdocumentconsumer-closesender">IXpsDocumentConsumer::CloseSender</a> to shut down the pipeline. Calling <b>IXpsDocumentConsumer::CloseSender</b> first can produce an invalid XPS document and cause an error.

