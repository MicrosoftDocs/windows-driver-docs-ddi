---
UID: NN:printerextension.IPrinterScriptableStream
title: IPrinterScriptableStream
author: windows-driver-content
description: The IPrinterScriptableStream interface builds on IPrinterScriptableSequentialStream and adds IStream-like semantics.
old-location: print\iprinterscriptablestream.htm
old-project: print
ms.assetid: AD3CDF90-76ED-498B-8DE1-B191504EB415
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrinterScriptableStream, IPrinterScriptableStream interface [Print Devices], IPrinterScriptableStream interface [Print Devices], described, print.iprinterscriptablestream, printerextension/IPrinterScriptableStream
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	Printerextension.h
api_name:
-	IPrinterScriptableStream
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterScriptableStream interface


## -description


The IPrinterScriptableStream interface builds on <a href="..\printerextension\nn-printerextension-iprinterscriptablesequentialstream.md">IPrinterScriptableSequentialStream</a> and adds IStream-like semantics.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterScriptableStream</b> interface inherits from <a href="..\printerextension\nn-printerextension-iprinterscriptablesequentialstream.md">IPrinterScriptableSequentialStream</a>. <b>IPrinterScriptableStream</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrinterScriptableStream</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439717">Commit</a>
</td>
<td align="left" width="63%">
Commits the operation.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439723">Seek</a>
</td>
<td align="left" width="63%">
Sets the seek pointer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439729">SetSize</a>
</td>
<td align="left" width="63%">
Sets the size of the scriptable stream, in bytes.

</td>
</tr>
</table> 


## -see-also

<a href="..\printerextension\nn-printerextension-iprinterscriptablepropertybag.md">IPrinterScriptablePropertyBag</a>



<a href="https://msdn.microsoft.com/493E6C55-DC3B-4160-9642-BDABADD575B8">IPrinterScriptablePropertyBag::GetReadStream</a>



<a href="https://msdn.microsoft.com/EFF55B5C-55E2-4E03-9D96-FDB1BC550A53">IPrinterScriptablePropertyBag::GetWriteStream</a>



<a href="..\printerextension\nn-printerextension-iprinterscriptablesequentialstream.md">IPrinterScriptableSequentialStream</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterScriptableStream interface%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

