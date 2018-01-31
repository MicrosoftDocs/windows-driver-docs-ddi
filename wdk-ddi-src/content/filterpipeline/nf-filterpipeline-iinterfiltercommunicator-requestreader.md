---
UID: NF:filterpipeline.IInterFilterCommunicator.RequestReader
title: IInterFilterCommunicator::RequestReader method
author: windows-driver-content
description: The RequestReader method retrieves the reader interface for an IInterFilterCommunicator object.
old-location: print\iinterfiltercommunicator_requestreader.htm
old-project: print
ms.assetid: 2b38b1b7-0d65-4457-bc7d-c52ff11aba48
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: IInterFilterCommunicator, RequestReader, RequestReader method [Print Devices], IInterFilterCommunicator interface, filterpipeline_dba6ebe4-7acb-471e-80e4-cedc8c2523b0.xml, IInterFilterCommunicator::RequestReader, print.iinterfiltercommunicator_requestreader, filterpipeline/IInterFilterCommunicator::RequestReader, IInterFilterCommunicator interface [Print Devices], RequestReader method, RequestReader method [Print Devices]
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
req.lib: filterpipeline.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	filterpipeline.h
apiname:
-	IInterFilterCommunicator.RequestReader
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IInterFilterCommunicator::RequestReader method


## -description


The <b>RequestReader</b> method retrieves the reader interface for an <b>IInterFilterCommunicator</b> object. 


## -syntax


````
HRESULT RequestReader(
  [out] void **ppIReader
);
````


## -parameters




#### - ppIReader [out]

A variable that receives the reader interface object when <b>RequestReader</b> retrieves.


## -returns


<b>RequestReader </b>returns an <b>HRESULT</b> value.



## -remarks


The <b>IInterFilterCommunicator</b> object is passed to each filter in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554291">IPrintPipelineFilter::InitializeFilter</a> method. The filter uses the <b>RequestReader</b> method to get the reader interface for the object. The universally unique identifier (UUID) for the object is declared in the <a href="https://msdn.microsoft.com/586247bd-6d06-4728-a5f0-ee3fe1d09321">filter pipeline configuration file</a>. The filter uses the <b>IInterFilterCommunicator</b> interface to receive input data.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554291">IPrintPipelineFilter::InitializeFilter</a>

<a href="..\filterpipeline\nn-filterpipeline-iinterfiltercommunicator.md">IInterFilterCommunicator</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IInterFilterCommunicator::RequestReader method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

