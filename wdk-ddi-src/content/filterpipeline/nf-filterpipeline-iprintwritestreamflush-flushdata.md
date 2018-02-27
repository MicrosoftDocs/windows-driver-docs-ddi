---
UID: NF:filterpipeline.IPrintWriteStreamFlush.FlushData
title: IPrintWriteStreamFlush::FlushData method
author: windows-driver-content
description: The FlushData method flushes buffered data to a data stream while leaving the stream open, allowing the caller to write additional data to the stream.
old-location: print\iprintwritestreamflush_flushdata.htm
old-project: print
ms.assetid: F0E31AA1-47BD-4294-89BA-27B02FC8125B
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: FlushData method [Print Devices], FlushData method [Print Devices], IPrintWriteStreamFlush interface, FlushData,IPrintWriteStreamFlush.FlushData, IPrintWriteStreamFlush, IPrintWriteStreamFlush interface [Print Devices], FlushData method, IPrintWriteStreamFlush::FlushData, filterpipeline/IPrintWriteStreamFlush::FlushData, print.iprintwritestreamflush_flushdata
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
-	IPrintWriteStreamFlush.FlushData
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IPrintWriteStreamFlush::FlushData method


## -description


The FlushData method flushes buffered data to a data stream while leaving the stream open, allowing the caller to write additional data to the stream.Writing to the stream is done using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554394">IPrintWriteStream::WriteBytes</a> method.


## -syntax


````
HRESULT FlushData(
    None
);
````


## -parameters






#### - None

None


## -returns



The FlushData method returns an HRESULT value.




## -remarks



Only the last filter in the print filter pipeline benefits from the flush. The data is flushed to the port monitor. However, the port monitor has the option of using  buffers.


#### Examples

The following code snippet shows how to flush data to a data stream. Note that error checking has been omitted for clarity.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>// Flushing data to a data stream
// ------------------------------
// Declare a pointer to an IPrintWriteStreamFlush interface
IPrintWriteStreamFlush *pIFlush;

// Retireve a pointer to an IPrintWriteStream interface 
// by using the RequestWriter() method in InitializeFilter()
IPrintWriteStream      *pIWrite;

HRESULT hr = pIWrite-&gt;QueryInterface(IID_IPrintWriteStreamFlush, reinterpret_cast&lt;void **&gt;(&amp;pIFlush));

hr = pIWrite-&gt;WriteBytes(buf, cb, &amp;cbWritten);

hr = pIFlush-&gt;FlushData();
</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554394">IPrintWriteStream::WriteBytes</a>



<a href="..\filterpipeline\nn-filterpipeline-iprintwritestreamflush.md">IPrintWriteStreamFlush</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintWriteStreamFlush::FlushData method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

