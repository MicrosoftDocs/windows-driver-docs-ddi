---
UID: NN:filterpipeline.IPrintReadStreamFactory
title: IPrintReadStreamFactory (filterpipeline.h)
description: The IPrintReadStreamFactory interface creates a stream reader that a filter can use to access the stream. For example, a filter could use this stream to access the per-user print ticket.
old-location: print\iprintreadstreamfactory.htm
tech.root: print
ms.assetid: 91f82cab-64c4-4f25-bf9a-b0757b1a83ca
ms.date: 04/20/2018
ms.keywords: IPrintReadStreamFactory, IPrintReadStreamFactory interface [Print Devices], IPrintReadStreamFactory interface [Print Devices],described, filterpipeline/IPrintReadStreamFactory, filterpipeline_6e71f042-ebb2-4a81-91ac-2dbfb8fd2161.xml, print.iprintreadstreamfactory
ms.topic: interface
f1_keywords:
 - "filterpipeline/IPrintReadStreamFactory"
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
- IPrintReadStreamFactory
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintReadStreamFactory interface


## -description


The <code>IPrintReadStreamFactory</code> interface creates a stream reader that a filter can use to access the stream. For example, a filter could use this stream to access the per-user print ticket.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintReadStreamFactory</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPrintReadStreamFactory</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintReadStreamFactory</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-iprintreadstreamfactory-getstream">IPrintReadStreamFactory::GetStream</a>
</td>
<td align="left" width="63%">
The <code>GetStream</code> method gets the stream interface.

</td>
</tr>
</table> 

