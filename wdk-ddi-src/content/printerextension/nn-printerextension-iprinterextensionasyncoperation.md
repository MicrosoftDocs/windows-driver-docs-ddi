---
UID: NN:printerextension.IPrinterExtensionAsyncOperation
title: IPrinterExtensionAsyncOperation (printerextension.h)
description: Provides the context associated with an asynchronous operation.
old-location: print\iprinterextensionasyncoperation.htm
tech.root: print
ms.assetid: AA862667-42D6-4A82-9698-1C43E9EEC434
ms.date: 04/20/2018
ms.keywords: IPrinterExtensionAsyncOperation, IPrinterExtensionAsyncOperation interface [Print Devices], IPrinterExtensionAsyncOperation interface [Print Devices],described, print.iprinterextensionasyncoperation, printerextension/IPrinterExtensionAsyncOperation
ms.topic: interface
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	IPrinterExtensionAsyncOperation
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterExtensionAsyncOperation interface


## -description


Provides the context associated with an asynchronous operation.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterExtensionAsyncOperation</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPrinterExtensionAsyncOperation</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrinterExtensionAsyncOperation</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406716">Cancel</a>
</td>
<td align="left" width="63%">
Cancels the asynchronous operation.

</td>
</tr>
</table> 


## -remarks



<b>IPrinterExtensionAsyncOperation</b> also helps to make it possible to perform device maintenance from a UWP device app or from a printer extension. For more information, see <a href="https://msdn.microsoft.com/310E92A9-F751-4346-9B2D-0578A136AD20">Device Maintenance</a>.




## -see-also




<a href="https://msdn.microsoft.com/310E92A9-F751-4346-9B2D-0578A136AD20">Device Maintenance</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265391">SendBidiSetRequestAsync</a>
 

 

