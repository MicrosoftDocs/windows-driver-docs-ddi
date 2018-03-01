---
UID: NF:filterpipeline.IXpsDocumentConsumer.SendXpsDocument
title: IXpsDocumentConsumer::SendXpsDocument method
author: windows-driver-content
description: The SendXpsDocument method sends an XPS document to the pipeline.
old-location: print\ixpsdocumentconsumer_sendxpsdocument.htm
old-project: print
ms.assetid: ad9f0f6b-19a6-4c99-9350-7ca249cf4774
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IXpsDocumentConsumer, IXpsDocumentConsumer interface [Print Devices], SendXpsDocument method, IXpsDocumentConsumer::SendXpsDocument, SendXpsDocument method [Print Devices], SendXpsDocument method [Print Devices], IXpsDocumentConsumer interface, SendXpsDocument,IXpsDocumentConsumer.SendXpsDocument, filterpipeline/IXpsDocumentConsumer::SendXpsDocument, filterpipeline_f8816c77-a8d0-4d44-bd12-adaf9194c34c.xml, print.ixpsdocumentconsumer_sendxpsdocument
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	filterpipeline.h
api_name:
-	IXpsDocumentConsumer.SendXpsDocument
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IXpsDocumentConsumer::SendXpsDocument method


## -description


The <code>SendXpsDocument</code> method sends an XPS document to the pipeline. 


## -syntax


````
HRESULT SendXpsDocument(
  [in] IXpsDocument *pIXpsDocument
);
````


## -parameters




### -param pIXpsDocument [in]

A pointer to the XPS document object to send.


## -returns



<code>SendXpsDocument</code> returns an <b>HRESULT</b> value.




## -remarks



The <a href="..\filterpipeline\nn-filterpipeline-ixpsdocument.md">IXpsDocument</a> interface is the root for a tree view of an XPS document. The tree also contains one fixed document sequence and any number of fixed documents and fixed pages.

Only one XpsDocument interface can be sent. The <code>SendXpsDocument</code> method will fail if a filter submits more than one XpsDocument interface for the same print job.




## -see-also

<a href="..\filterpipeline\nn-filterpipeline-ixpsdocument.md">IXpsDocument</a>



<a href="..\filterpipeline\nn-filterpipeline-ixpsdocumentconsumer.md">IXpsDocumentConsumer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IXpsDocumentConsumer::SendXpsDocument method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

