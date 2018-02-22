---
UID: NN:filterpipeline.IPrintWriteStream
title: IPrintWriteStream
author: windows-driver-content
description: Filters use the IPrintWriteStream interface to write data as a raw stream of bytes.
old-location: print\iprintwritestream.htm
old-project: print
ms.assetid: b76a58fb-fbd4-4afe-83dc-582242b53e05
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: print.iprintwritestream, IPrintWriteStream interface [Print Devices], IPrintWriteStream interface [Print Devices], described, IPrintWriteStream, filterpipeline/IPrintWriteStream, filterpipeline_edf6ac16-09e1-433a-8f41-50ba308dc7a7.xml
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
-	IPrintWriteStream
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IPrintWriteStream interface


## -description


Filters use the <code>IPrintWriteStream</code> interface to write data as a raw stream of bytes.


## -members

The <b>IPrintWriteStream</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554391">IPrintWriteStream::Close</a>
</td>
<td align="left" width="63%">
The <code>Close</code> method closes a stream and ends the writing to that stream. This method is mandatory. You must call this method when the filter is done writing.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554394">IPrintWriteStream::WriteBytes</a>
</td>
<td align="left" width="63%">
The <code>WriteBytes</code> method writes a specified number of bytes to a stream.

</td>
</tr>
</table>The <code>Close</code> method closes a stream and ends the writing to that stream. This method is mandatory. You must call this method when the filter is done writing.

The <code>WriteBytes</code> method writes a specified number of bytes to a stream.

 

