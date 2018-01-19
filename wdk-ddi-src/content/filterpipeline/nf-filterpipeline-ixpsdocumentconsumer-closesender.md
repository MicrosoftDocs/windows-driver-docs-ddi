---
UID: NF:filterpipeline.IXpsDocumentConsumer.CloseSender
title: IXpsDocumentConsumer::CloseSender method
author: windows-driver-content
description: The CloseSender method tells the Pipeline Manager that the filter is done sending XPS parts.
old-location: print\ixpsdocumentconsumer_closesender.htm
old-project: print
ms.assetid: b9a860b1-d169-44b6-8dbd-0d26b050b7b0
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IXpsDocumentConsumer, IXpsDocumentConsumer::CloseSender, CloseSender
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
req.alt-api: IXpsDocumentConsumer.CloseSender
req.alt-loc: Filterpipeline.h
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

# IXpsDocumentConsumer::CloseSender method



## -description
The <code>CloseSender</code> method tells the Pipeline Manager that the filter is done sending XPS parts.



## -syntax

````
HRESULT STDMETHODCALLTYPE CloseSender(
    None
);
````


## -parameters

### -param None 


## -returns
None


## -remarks
The filter must call the <code>CloseSender</code> method when it has finished sending the XPS parts to the pipeline.</p>