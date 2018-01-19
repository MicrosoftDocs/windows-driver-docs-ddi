---
UID: NN:filterpipeline.IPrintReadStream
title: IPrintReadStream
author: windows-driver-content
description: Filters use the IPrintReadStream interface to read data as a raw stream of bytes.
old-location: print\iprintreadstream.htm
old-project: print
ms.assetid: f31a6547-44ec-4331-8f9b-e46192f4966a
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IXpsPartIterator, IXpsPartIterator::Reset, Reset
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
req.alt-api: IPrintReadStream
req.alt-loc: filterpipeline.h
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
req.typenames: EXpsFontRestriction
---

# IPrintReadStream interface



## -description
Filters use the <code>IPrintReadStream</code> interface to read data as a raw stream of bytes.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintReadStream</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IPrintReadStream</b> also has these types of members:

The <b>IPrintReadStream</b> interface has these methods.

The <code>ReadBytes</code> method reads a number of bytes into a buffer.

The <code>Seek</code> method changes the seek pointer to a new location in the stream.

 


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
</table>The <code>ReadBytes</code> method reads a number of bytes into a buffer.

The <code>Seek</code> method changes the seek pointer to a new location in the stream.

 


## -remarks
