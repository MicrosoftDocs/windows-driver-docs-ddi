---
UID: NF:filterpipeline.IInterFilterCommunicator.RequestWriter
title: IInterFilterCommunicator::RequestWriter (filterpipeline.h)
description: The RequestWriter method retrieves the writer interface for an IInterFilterCommunicator object.
old-location: print\iinterfiltercommunicator_requestwriter.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IInterFilterCommunicator::RequestWriter"]
ms.keywords: IInterFilterCommunicator interface [Print Devices],RequestWriter method, IInterFilterCommunicator.RequestWriter, IInterFilterCommunicator::RequestWriter, RequestWriter, RequestWriter method [Print Devices], RequestWriter method [Print Devices],IInterFilterCommunicator interface, filterpipeline/IInterFilterCommunicator::RequestWriter, filterpipeline_b2f3eac2-d759-45b4-818b-4d828c5aeedc.xml, print.iinterfiltercommunicator_requestwriter
req.header: filterpipeline.h
req.include-header: Filterpipeline.h
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
 - IInterFilterCommunicator::RequestWriter
 - filterpipeline/IInterFilterCommunicator::RequestWriter
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - filterpipeline.h
api_name:
 - IInterFilterCommunicator.RequestWriter
---

# IInterFilterCommunicator::RequestWriter


## -description

The <b>RequestWriter</b> method retrieves the writer interface for an <b>IInterFilterCommunicator</b> object.

## -parameters

### -param ppIWriter 

[out]
A variable that receives the writer interface object that <b>RequestWriter</b> retrieves.

## -returns

<b>RequestWriter</b> returns an <b>HRESULT</b> value.

## -remarks

The <b>IInterFilterCommunicator</b> object is passed to each filter in the <a href="/windows-hardware/drivers/ddi/filterpipeline/nf-filterpipeline-iprintpipelinefilter-initializefilter">IPrintPipelineFilter::InitializeFilter</a> method. The filter uses the <b>RequestWriter</b> method to get the writer interface for the object. The universally unique identifier (UUID) for the object is declared in the <a href="/windows-hardware/drivers/print/filter-pipeline-configuration-file">filter pipeline configuration file</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/filterpipeline/nn-filterpipeline-iinterfiltercommunicator">IInterFilterCommunicator</a>



<a href="/windows-hardware/drivers/ddi/filterpipeline/nf-filterpipeline-iprintpipelinefilter-initializefilter">IPrintPipelineFilter::InitializeFilter</a>
