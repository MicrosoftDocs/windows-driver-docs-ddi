---
UID: NN:printerextension.IPrinterScriptablePropertyBag
title: IPrinterScriptablePropertyBag
author: windows-driver-content
description: The IPrinterScriptablePropertyBag interface is the property bag interface passed to script clients.
old-location: print\iprinterscriptablepropertybag.htm
tech.root: print
ms.assetid: E6F48895-7ED6-479B-BF16-42192461C56D
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: IPrinterScriptablePropertyBag, IPrinterScriptablePropertyBag interface [Print Devices], IPrinterScriptablePropertyBag interface [Print Devices],described, print.iprinterscriptablepropertybag, printerextension/IPrinterScriptablePropertyBag
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
-	IPrinterScriptablePropertyBag
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterScriptablePropertyBag interface


## -description


The IPrinterScriptablePropertyBag interface is the property bag interface passed to script clients. 

This interface is the same as <a href="https://msdn.microsoft.com/library/windows/hardware/hh439547">IPrinterPropertyBag</a>, except that the GetBytes and SetBytes methods operate on JavaScript arrays and the GetReadStream and GetWriteStream methods operate on <a href="https://msdn.microsoft.com/library/windows/hardware/hh973218">IPrinterScriptableStream</a> objects.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterScriptablePropertyBag</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPrinterScriptablePropertyBag</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrinterScriptablePropertyBag</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439647">GetBool</a>
</td>
<td align="left" width="63%">
Gets a specified boolean property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439653">GetBytes</a>
</td>
<td align="left" width="63%">
Gets a byte array property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439658">GetInt32</a>
</td>
<td align="left" width="63%">
Gets an integer property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439535">GetReadStream</a>
</td>
<td align="left" width="63%">
Gets a read stream and uses it to read  from a property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983419">GetString</a>
</td>
<td align="left" width="63%">
Gets a string property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439675">GetWriteStream</a>
</td>
<td align="left" width="63%">
Gets a stream and uses it  to write to a stream property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439552">SetBool</a>
</td>
<td align="left" width="63%">
Writes a specified boolean property value.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439606">SetBytes</a>
</td>
<td align="left" width="63%">
Writes a byte array property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439610">SetInt32</a>
</td>
<td align="left" width="63%">
Writes an integer property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj983427">SetString</a>
</td>
<td align="left" width="63%">
Writes a string property.

</td>
</tr>
</table> 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439547">IPrinterPropertyBag</a>



<a href="https://msdn.microsoft.com/73BE6E2A-0C46-4C3F-8888-5FE8386A1F50">IPrinterScriptContext::DriverProperties</a>



<a href="https://msdn.microsoft.com/EEC61313-5796-42BC-84BF-CF29F8BE0C96">IPrinterScriptContext::QueueProperties</a>



<a href="https://msdn.microsoft.com/6F181350-41A3-4592-BB72-1E3AD6FEC748">IPrinterScriptContext::UserProperties</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh973218">IPrinterScriptableStream</a>



<a href="https://msdn.microsoft.com/4E20303A-BEB3-4928-BA5A-356D978FA2BE">V4 Printer Driver Property Bags</a>
 

 

