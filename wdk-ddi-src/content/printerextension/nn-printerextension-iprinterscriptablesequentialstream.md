---
UID: NN:printerextension.IPrinterScriptableSequentialStream
title: IPrinterScriptableSequentialStream (printerextension.h)
description: The IPrinterScriptableSequentialStream interface is an ISequentialStream-like interface that works in JavaScript. Instead of reading and writing byte arrays, it reads and writes JavaScript arrays of bytes, which are values between 0 and 255.
old-location: print\iprinterscriptablesequentialstream_interface.htm
tech.root: print
ms.assetid: 85DF7DCB-7AB1-4A46-AD70-6D47D9F98079
ms.date: 04/20/2018
ms.keywords: IPrinterScriptableSequentialStream, IPrinterScriptableSequentialStream interface [Print Devices], IPrinterScriptableSequentialStream interface [Print Devices],described, print.iprinterscriptablesequentialstream_interface, printerextension/IPrinterScriptableSequentialStream
ms.topic: interface
req.header: printerextension.h
req.include-header: 
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	printerextension.h
api_name:
-	IPrinterScriptableSequentialStream
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterScriptableSequentialStream interface


## -description


The IPrinterScriptableSequentialStream interface is an ISequentialStream-like interface that works in JavaScript. Instead of reading and writing byte arrays, it reads and writes JavaScript arrays of bytes, which are values between 0 and 255. 


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterScriptableSequentialStream</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPrinterScriptableSequentialStream</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrinterScriptableSequentialStream</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439702">Read</a>
</td>
<td align="left" width="63%">
The Read method reads bytes from the stream and returns them as a JavaScript array.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439706">Write</a>
</td>
<td align="left" width="63%">
The Write method writes the provided JavaScript array to the stream and returns the number of bytes written.

</td>
</tr>
</table> 

