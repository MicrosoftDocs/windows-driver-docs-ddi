---
UID: NN:filterpipeline.IPrintReadStreamFactory
title: IPrintReadStreamFactory
author: windows-driver-content
description: The IPrintReadStreamFactory interface creates a stream reader that a filter can use to access the stream. For example, a filter could use this stream to access the per-user print ticket.
old-location: print\iprintreadstreamfactory.htm
old-project: print
ms.assetid: 91f82cab-64c4-4f25-bf9a-b0757b1a83ca
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: print.iprintreadstreamfactory, IPrintReadStreamFactory interface [Print Devices], IPrintReadStreamFactory interface [Print Devices], described, IPrintReadStreamFactory, filterpipeline/IPrintReadStreamFactory, filterpipeline_6e71f042-ebb2-4a81-91ac-2dbfb8fd2161.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
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
-	IPrintReadStreamFactory
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IPrintReadStreamFactory interface


## -description


The <code>IPrintReadStreamFactory</code> interface creates a stream reader that a filter can use to access the stream. For example, a filter could use this stream to access the per-user print ticket.


## -members

The <b>IPrintReadStreamFactory</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554343">IPrintReadStreamFactory::GetStream</a>
</td>
<td align="left" width="63%">
The <code>GetStream</code> method gets the stream interface.

</td>
</tr>
</table>The <code>GetStream</code> method gets the stream interface.

 

