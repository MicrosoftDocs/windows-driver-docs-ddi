---
UID: NF:filterpipeline.IInterFilterCommunicator.RequestWriter
title: IInterFilterCommunicator::RequestWriter method
author: windows-driver-content
description: The RequestWriter method retrieves the writer interface for an IInterFilterCommunicator object.
old-location: print\iinterfiltercommunicator_requestwriter.htm
old-project: print
ms.assetid: 1f0684f0-e15e-491f-ba09-314f831d7ba9
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: IInterFilterCommunicator interface [Print Devices], RequestWriter method, RequestWriter method [Print Devices], IInterFilterCommunicator interface, IInterFilterCommunicator, RequestWriter, IInterFilterCommunicator::RequestWriter, filterpipeline_b2f3eac2-d759-45b4-818b-4d828c5aeedc.xml, print.iinterfiltercommunicator_requestwriter, RequestWriter method [Print Devices], filterpipeline/IInterFilterCommunicator::RequestWriter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	IInterFilterCommunicator.RequestWriter
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IInterFilterCommunicator::RequestWriter method


## -description


The <b>RequestWriter</b> method retrieves the writer interface for an <b>IInterFilterCommunicator</b> object.


## -syntax


````
HRESULT RequestWriter(
  [out] void **ppIWriter
);
````


## -parameters




### -param ppIWriter [out]

A variable that receives the writer interface object that <b>RequestWriter</b> retrieves.


## -returns


<b>RequestWriter</b> returns an <b>HRESULT</b> value.



## -remarks


The <b>IInterFilterCommunicator</b> object is passed to each filter in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554291">IPrintPipelineFilter::InitializeFilter</a> method. The filter uses the <b>RequestWriter</b> method to get the writer interface for the object. The universally unique identifier (UUID) for the object is declared in the <a href="https://msdn.microsoft.com/586247bd-6d06-4728-a5f0-ee3fe1d09321">filter pipeline configuration file</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554291">IPrintPipelineFilter::InitializeFilter</a>

<a href="..\filterpipeline\nn-filterpipeline-iinterfiltercommunicator.md">IInterFilterCommunicator</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IInterFilterCommunicator::RequestWriter method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

