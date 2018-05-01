---
UID: NN:filterpipeline.IPrintWriteStreamFlush
title: IPrintWriteStreamFlush
author: windows-driver-content
description: Filters use the IPrintWriteStreamFlush interface to explicitly flush data as a raw stream of bytes from a filter. This interface is retrieved through IPrintWriteStream::QueryInterface().
old-location: print\iprintwritestreamflush.htm
old-project: print
ms.assetid: DB3E1127-B3B1-4C48-9819-EEF705B9985A
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: IPrintWriteStreamFlush, IPrintWriteStreamFlush interface [Print Devices], IPrintWriteStreamFlush interface [Print Devices],described, filterpipeline/IPrintWriteStreamFlush, print.iprintwritestreamflush
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	filterpipeline.h
api_name:
-	IPrintWriteStreamFlush
product: Windows
targetos: Windows
req.typenames: 
---

# IPrintWriteStreamFlush interface


## -description


Filters use the IPrintWriteStreamFlush interface to explicitly flush data as a raw stream of bytes from a filter.  This interface is retrieved through IPrintWriteStream::QueryInterface().


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintWriteStreamFlush</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPrintWriteStreamFlush</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintWriteStreamFlush</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh768283">FlushData</a>
</td>
<td align="left" width="63%">
The FlushData method flushes buffered data to a data stream while leaving the stream open, allowing the caller to write additional data to the stream.

</td>
</tr>
</table> 

