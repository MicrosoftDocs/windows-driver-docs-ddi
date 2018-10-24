---
UID: NF:filterpipeline.IXpsDocumentConsumer.SendFixedDocumentSequence
title: IXpsDocumentConsumer::SendFixedDocumentSequence
author: windows-driver-content
description: The SendFixedDocumentSequence method sends a fixed document sequence to the pipeline.
old-location: print\ixpsdocumentconsumer_sendfixeddocumentsequence.htm
tech.root: print
ms.assetid: e2541943-7e0c-45ca-bdfe-2d48581f62a4
ms.date: 04/20/2018
ms.keywords: IXpsDocumentConsumer interface [Print Devices],SendFixedDocumentSequence method, IXpsDocumentConsumer.SendFixedDocumentSequence, IXpsDocumentConsumer::SendFixedDocumentSequence, SendFixedDocumentSequence, SendFixedDocumentSequence method [Print Devices], SendFixedDocumentSequence method [Print Devices],IXpsDocumentConsumer interface, filterpipeline/IXpsDocumentConsumer::SendFixedDocumentSequence, filterpipeline_cd741d5b-4069-4a67-8add-b5c2701699f6.xml, print.ixpsdocumentconsumer_sendfixeddocumentsequence
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
-	IXpsDocumentConsumer.SendFixedDocumentSequence
product:
- Windows
targetos: Windows
req.typenames: 
---

# IXpsDocumentConsumer::SendFixedDocumentSequence


## -description


The <b>SendFixedDocumentSequence</b> method sends a fixed document sequence to the pipeline.


## -parameters




### -param pIFixedDocumentSequence [in]

A pointer to an XPS fixed document sequence object.


## -returns



<code>SendFixedDocumentSequence</code> returns an <b>HRESULT</b> value.




## -remarks



Only one <a href="https://msdn.microsoft.com/library/windows/hardware/ff550972">IFixedDocumentSequence</a> interface can be sent. The <code>SendFixedDocumentSequence</code> method will fail if a filter submits more than one such interface for the same print job.



