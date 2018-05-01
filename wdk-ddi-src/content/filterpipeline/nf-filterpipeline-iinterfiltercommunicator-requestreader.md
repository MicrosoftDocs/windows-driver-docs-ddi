---
UID: NF:filterpipeline.IInterFilterCommunicator.RequestReader
title: IInterFilterCommunicator::RequestReader
author: windows-driver-content
description: The RequestReader method retrieves the reader interface for an IInterFilterCommunicator object.
old-location: print\iinterfiltercommunicator_requestreader.htm
old-project: print
ms.assetid: 2b38b1b7-0d65-4457-bc7d-c52ff11aba48
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: IInterFilterCommunicator interface [Print Devices],RequestReader method, IInterFilterCommunicator.RequestReader, IInterFilterCommunicator::RequestReader, RequestReader, RequestReader method [Print Devices], RequestReader method [Print Devices],IInterFilterCommunicator interface, filterpipeline/IInterFilterCommunicator::RequestReader, filterpipeline_dba6ebe4-7acb-471e-80e4-cedc8c2523b0.xml, print.iinterfiltercommunicator_requestreader
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	filterpipeline.h
api_name:
-	IInterFilterCommunicator.RequestReader
product: Windows
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



The <b>IInterFilterCommunicator</b> object is passed to each filter in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554291">IPrintPipelineFilter::InitializeFilter</a> method. The filter uses the <b>RequestReader</b> method to get the reader interface for the object. The universally unique identifier (UUID) for the object is declared in the <a href="https://msdn.microsoft.com/586247bd-6d06-4728-a5f0-ee3fe1d09321">filter pipeline configuration file</a>. The filter uses the <b>IInterFilterCommunicator</b> interface to receive input data.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551050">IInterFilterCommunicator</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554291">IPrintPipelineFilter::InitializeFilter</a>
 

 

