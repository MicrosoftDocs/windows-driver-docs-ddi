---
UID: NN:printerextension.IPrinterExtensionContextCollection
title: IPrinterExtensionContextCollection (printerextension.h)
description: Exposes a collection of IPrinterExtensionContext objects.
old-location: print\iprinterextensioncontextcollection.htm
tech.root: print
ms.assetid: 693DAA13-70B3-48A7-9BC2-6369691539FD
ms.date: 04/20/2018
ms.keywords: IPrinterExtensionContextCollection, IPrinterExtensionContextCollection interface [Print Devices], IPrinterExtensionContextCollection interface [Print Devices],described, print.iprinterextensioncontextcollection, printerextension/IPrinterExtensionContextCollection
ms.topic: interface
f1_keywords:
 - "printerextension/IPrinterExtensionContextCollection"
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
- IPrinterExtensionContextCollection
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterExtensionContextCollection interface


## -description


Exposes a collection of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprinterextensioncontext">IPrinterExtensionContext</a> objects.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterExtensionContextCollection</b> interface inherits from the <a href="ebbff4bc-36b2-4861-9efa-ffa45e013eb5">IDispatch</a> interface. <b>IPrinterExtensionContextCollection</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
<li><a href="https://docs.microsoft.com/">Properties</a></li>
</ul>

## -members

The <b>IPrinterExtensionContextCollection</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterextensioncontextcollection-get__newenum">get__NewEnum</a>
</td>
<td align="left" width="63%">
Gets a pointer to the enumerants of <b>IPrinterExtensionContextCollection</b> objects.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/previous-versions/windows/hardware/radio/hh406567(v=vs.85)">GetAt</a>
</td>
<td align="left" width="63%">
Gets a pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprinterextensioncontext">IPrinterExtensionContext</a> object.

</td>
</tr>
</table> 
<h3><a id="properties"></a>Properties</h3>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterExtensionContextCollection</b> interface has these properties.
<table class="members" id="memberListProperties">
<tr>
<th align="left" width="27%">Property</th>
<th align="left" width="10%">Access type</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/hh406342(v=vs.85)">Count</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets a count of the number of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprinterextensioncontext">IPrinterExtensionContext</a> objects in the collection.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch">IDispatch</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprinterextensioncontext">IPrinterExtensionContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterextensionevent-onprinterqueuesenumerated">IPrinterExtensionEvent::OnPrinterQueuesEnumerated</a>
 

 

