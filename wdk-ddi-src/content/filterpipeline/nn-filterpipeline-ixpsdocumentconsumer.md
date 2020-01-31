---
UID: NN:filterpipeline.IXpsDocumentConsumer
title: IXpsDocumentConsumer (filterpipeline.h)
description: A filter uses the IXpsDocumentConsumer interface when it generates XPS content for the pipeline to consume.
old-location: print\ixpsdocumentconsumer.htm
tech.root: print
ms.assetid: 98e603e6-2786-4bc8-ad8a-0e91b0d444d8
ms.date: 04/20/2018
ms.keywords: IXpsDocumentConsumer, IXpsDocumentConsumer interface [Print Devices], IXpsDocumentConsumer interface [Print Devices],described, filterpipeline/IXpsDocumentConsumer, filterpipeline_230eb0f6-427a-4986-b8ad-bc1d41853d67.xml, print.ixpsdocumentconsumer
f1_keywords:
 - "filterpipeline/IXpsDocumentConsumer"
req.header: filterpipeline.h
req.include-header: Filterpipeline.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
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
- IXpsDocumentConsumer
product:
- Windows
targetos: Windows
req.typenames: 
---

# IXpsDocumentConsumer interface


## -description


A filter uses the <code>IXpsDocumentConsumer</code> interface when it generates XPS content for the pipeline to consume. 
<div class="alert"><b>Note</b>    The XPS print filter pipeline does not preserve digital signatures or story fragments. You may be able to work around this by using stream filters.</div><div> </div>

## -inheritance

The <b xmlns:loc="https://microsoft.com/wdcml/l10n">IXpsDocumentConsumer</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IXpsDocumentConsumer</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

