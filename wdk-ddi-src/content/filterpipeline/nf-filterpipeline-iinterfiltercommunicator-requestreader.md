---
UID: NF:filterpipeline.IInterFilterCommunicator.RequestReader
title: IInterFilterCommunicator::RequestReader (filterpipeline.h)
description: The RequestReader method retrieves the reader interface for an IInterFilterCommunicator object.
old-location: print\iinterfiltercommunicator_requestreader.htm
tech.root: print
ms.assetid: 2b38b1b7-0d65-4457-bc7d-c52ff11aba48
ms.date: 04/20/2018
ms.keywords: IInterFilterCommunicator interface [Print Devices],RequestReader method, IInterFilterCommunicator.RequestReader, IInterFilterCommunicator::RequestReader, RequestReader, RequestReader method [Print Devices], RequestReader method [Print Devices],IInterFilterCommunicator interface, filterpipeline/IInterFilterCommunicator::RequestReader, filterpipeline_dba6ebe4-7acb-471e-80e4-cedc8c2523b0.xml, print.iinterfiltercommunicator_requestreader
ms.topic: method
f1_keywords:
 - "filterpipeline/IInterFilterCommunicator.RequestReader"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- filterpipeline.h
api_name:
- IInterFilterCommunicator.RequestReader
product:
- Windows
targetos: Windows
req.typenames: 
---

# IInterFilterCommunicator::RequestReader


## -description


The <b>RequestReader</b> method retrieves the reader interface for an <b>IInterFilterCommunicator</b> object. 


## -parameters




### -param ppIReader [out]

A variable that receives the reader interface object when <b>RequestReader</b> retrieves.


## -returns



<b>RequestReader </b>returns an <b>HRESULT</b> value.




## -remarks



The <b>IInterFilterCommunicator</b> object is passed to each filter in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/filterpipeline/nf-filterpipeline-iprintpipelinefilter-initializefilter">IPrintPipelineFilter::InitializeFilter</a> method. The filter uses the <b>RequestReader</b> method to get the reader interface for the object. The universally unique identifier (UUID) for the object is declared in the <a href="https://docs.microsoft.com/windows-hardware/drivers/print/filter-pipeline-configuration-file">filter pipeline configuration file</a>. The filter uses the <b>IInterFilterCommunicator</b> interface to receive input data.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/filterpipeline/nn-filterpipeline-iinterfiltercommunicator">IInterFilterCommunicator</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/filterpipeline/nf-filterpipeline-iprintpipelinefilter-initializefilter">IPrintPipelineFilter::InitializeFilter</a>
 

 

