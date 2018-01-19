---
UID: NF:filterpipeline.IXpsDocumentConsumer.SendFixedDocumentSequence
title: IXpsDocumentConsumer::SendFixedDocumentSequence method
author: windows-driver-content
description: The SendFixedDocumentSequence method sends a fixed document sequence to the pipeline.
old-location: print\ixpsdocumentconsumer_sendfixeddocumentsequence.htm
old-project: print
ms.assetid: e2541943-7e0c-45ca-bdfe-2d48581f62a4
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IXpsDocumentConsumer, IXpsDocumentConsumer::SendFixedDocumentSequence, SendFixedDocumentSequence
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
req.alt-api: IXpsDocumentConsumer.SendFixedDocumentSequence
req.alt-loc: filterpipeline.h
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
req.typenames: EXpsFontRestriction
---

# IXpsDocumentConsumer::SendFixedDocumentSequence method



## -description
The <b>SendFixedDocumentSequence</b> method sends a fixed document sequence to the pipeline.



## -syntax

````
HRESULT SendFixedDocumentSequence(
  [in] IFixedDocumentSequence *pIFixedDocumentSequence
);
````


## -parameters

### -param pIFixedDocumentSequence [in]

A pointer to an XPS fixed document sequence object.


## -returns
<code>SendFixedDocumentSequence</code> returns an <b>HRESULT</b> value.


## -remarks
Only one <a href="..\filterpipeline\nn-filterpipeline-ifixeddocumentsequence.md">IFixedDocumentSequence</a> interface can be sent. The <code>SendFixedDocumentSequence</code> method will fail if a filter submits more than one such interface for the same print job.</p>