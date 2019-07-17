---
UID: NN:printerextension.IPrinterScriptablePropertyBag
title: IPrinterScriptablePropertyBag (printerextension.h)
description: The IPrinterScriptablePropertyBag interface is the property bag interface passed to script clients.
old-location: print\iprinterscriptablepropertybag.htm
tech.root: print
ms.assetid: E6F48895-7ED6-479B-BF16-42192461C56D
ms.date: 04/20/2018
ms.keywords: IPrinterScriptablePropertyBag, IPrinterScriptablePropertyBag interface [Print Devices], IPrinterScriptablePropertyBag interface [Print Devices],described, print.iprinterscriptablepropertybag, printerextension/IPrinterScriptablePropertyBag
ms.topic: interface
f1_keywords:
 - "printerextension/IPrinterScriptablePropertyBag"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Printerextension.h
api_name:
- IPrinterScriptablePropertyBag
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterScriptablePropertyBag interface


## -description


The IPrinterScriptablePropertyBag interface is the property bag interface passed to script clients. 

This interface is the same as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprinterpropertybag">IPrinterPropertyBag</a>, except that the GetBytes and SetBytes methods operate on JavaScript arrays and the GetReadStream and GetWriteStream methods operate on <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprinterscriptablestream">IPrinterScriptableStream</a> objects.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterScriptablePropertyBag</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPrinterScriptablePropertyBag</b> also has these types of members:
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
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterscriptablepropertybag-getbool">GetBool</a>
</td>
<td align="left" width="63%">
Gets a specified boolean property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterscriptablepropertybag-getbytes">GetBytes</a>
</td>
<td align="left" width="63%">
Gets a byte array property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterscriptablepropertybag-getint32">GetInt32</a>
</td>
<td align="left" width="63%">
Gets an integer property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterpropertybag-getreadstream">GetReadStream</a>
</td>
<td align="left" width="63%">
Gets a read stream and uses it to read  from a property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nf-extsfns-idebugfailureanalysis2-getstring">GetString</a>
</td>
<td align="left" width="63%">
Gets a string property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterscriptablepropertybag-getwritestream">GetWriteStream</a>
</td>
<td align="left" width="63%">
Gets a stream and uses it  to write to a stream property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterpropertybag-setbool">SetBool</a>
</td>
<td align="left" width="63%">
Writes a specified boolean property value.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterpropertybag-setbytes">SetBytes</a>
</td>
<td align="left" width="63%">
Writes a byte array property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterpropertybag-setint32">SetInt32</a>
</td>
<td align="left" width="63%">
Writes an integer property.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nf-extsfns-idebugfailureanalysis2-setstring">SetString</a>
</td>
<td align="left" width="63%">
Writes a string property.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprinterpropertybag">IPrinterPropertyBag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterscriptcontext-get_driverproperties">IPrinterScriptContext::DriverProperties</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterscriptcontext-get_queueproperties">IPrinterScriptContext::QueueProperties</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterscriptcontext-get_userproperties">IPrinterScriptContext::UserProperties</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprinterscriptablestream">IPrinterScriptableStream</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/v4-driver-property-bags">V4 Printer Driver Property Bags</a>
 

 

