---
UID: NN:filterpipeline.IPrintReadStream
title: IPrintReadStream
author: windows-driver-content
description: Filters use the IPrintReadStream interface to read data as a raw stream of bytes.
old-location: print\iprintreadstream.htm
old-project: print
ms.assetid: f31a6547-44ec-4331-8f9b-e46192f4966a
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IPrintReadStream, IPrintReadStream interface [Print Devices], IPrintReadStream interface [Print Devices], described, filterpipeline/IPrintReadStream, filterpipeline_51454792-ccd6-4c55-adbc-d5cc1536f93c.xml, print.iprintreadstream
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
-	IPrintReadStream
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IPrintReadStream interface


## -description


Filters use the <code>IPrintReadStream</code> interface to read data as a raw stream of bytes.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintReadStream</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPrintReadStream</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintReadStream</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554347">IPrintReadStream::ReadBytes</a>
</td>
<td align="left" width="63%">
The <code>ReadBytes</code> method reads a number of bytes into a buffer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554350">IPrintReadStream::Seek</a>
</td>
<td align="left" width="63%">
The <code>Seek</code> method changes the seek pointer to a new location in the stream.

</td>
</tr>
</table> 

