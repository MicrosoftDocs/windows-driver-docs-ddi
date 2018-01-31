---
UID: NN:printerextension.IPrinterScriptablePropertyBag
title: IPrinterScriptablePropertyBag
author: windows-driver-content
description: The IPrinterScriptablePropertyBag interface is the property bag interface passed to script clients.
old-location: print\iprinterscriptablepropertybag.htm
old-project: print
ms.assetid: E6F48895-7ED6-479B-BF16-42192461C56D
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: print.iprinterscriptablepropertybag, IPrinterScriptablePropertyBag interface [Print Devices], IPrinterScriptablePropertyBag interface [Print Devices], described, IPrinterScriptablePropertyBag, printerextension/IPrinterScriptablePropertyBag
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
req.lib: printerextension.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Printerextension.h
apiname:
-	IPrinterScriptablePropertyBag
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterScriptablePropertyBag interface


## -description


The IPrinterScriptablePropertyBag interface is the property bag interface passed to script clients. 

This interface is the same as <a href="..\printerextension\nn-printerextension-iprinterpropertybag.md">IPrinterPropertyBag</a>, except that the GetBytes and SetBytes methods operate on JavaScript arrays and the GetReadStream and GetWriteStream methods operate on <a href="..\printerextension\nn-printerextension-iprinterscriptablestream.md">IPrinterScriptableStream</a> objects.


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
</table>Gets a specified boolean property.

Gets a byte array property.

Gets an integer property.

Gets a read stream and uses it to read  from a property.

Gets a string property.

Gets a stream and uses it  to write to a stream property.

Writes a specified boolean property value.

Writes a byte array property.

Writes an integer property.

Writes a string property.

 


## -see-also

<a href="..\printerextension\nn-printerextension-iprinterpropertybag.md">IPrinterPropertyBag</a>

<a href="https://msdn.microsoft.com/EEC61313-5796-42BC-84BF-CF29F8BE0C96">IPrinterScriptContext::QueueProperties</a>

<a href="https://msdn.microsoft.com/73BE6E2A-0C46-4C3F-8888-5FE8386A1F50">IPrinterScriptContext::DriverProperties</a>

<a href="https://msdn.microsoft.com/6F181350-41A3-4592-BB72-1E3AD6FEC748">IPrinterScriptContext::UserProperties</a>

<a href="https://msdn.microsoft.com/4E20303A-BEB3-4928-BA5A-356D978FA2BE">V4 Printer Driver Property Bags</a>

<a href="..\printerextension\nn-printerextension-iprinterscriptablestream.md">IPrinterScriptableStream</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterScriptablePropertyBag interface%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

