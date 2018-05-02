---
UID: NN:printerextension.IPrintSchemaOptionCollection
title: IPrintSchemaOptionCollection
author: windows-driver-content
description: Exposes a collection of IPrintSchemaOption objects.
old-location: print\iprintschemaoptioncollection.htm
old-project: print
ms.assetid: ED0FD042-EB42-4F4B-AF9C-B8F56909ED66
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: IPrintSchemaOptionCollection, IPrintSchemaOptionCollection interface [Print Devices], IPrintSchemaOptionCollection interface [Print Devices],described, print.iprintschemaoptioncollection, printerextension/IPrintSchemaOptionCollection
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
-	IPrintSchemaOptionCollection
product: Windows
targetos: Windows
req.typenames: 
---

# IPrintSchemaOptionCollection interface


## -description


Exposes a collection of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451335">IPrintSchemaOption</a> objects.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaOptionCollection</b> interface inherits from the <a href="ebbff4bc-36b2-4861-9efa-ffa45e013eb5">IDispatch</a> interface. <b>IPrintSchemaOptionCollection</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
<li><a href="https://docs.microsoft.com/">Properties</a></li>
</ul>

## -members

The <b>IPrintSchemaOptionCollection</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406567">GetAt</a>
</td>
<td align="left" width="63%">
Gets a pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451335">IPrintSchemaOption</a> object.

</td>
</tr>
</table> 
<h3><a id="properties"></a>Properties</h3>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaOptionCollection</b> interface has these properties.
<table class="members" id="memberListProperties">
<tr>
<th align="left" width="27%">Property</th>
<th align="left" width="10%">Access type</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406342">Count</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets a count of the number of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451335">IPrintSchemaOption</a> objects in the collection.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh973226">NewEnum</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets a pointer to the enumerants of <b>IPrintSchemaOptionCollection</b> objects.

</td>
</tr>
</table> 


## -see-also




<a href="https://msdn.microsoft.com/ebbff4bc-36b2-4861-9efa-ffa45e013eb5">IDispatch</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451335">IPrintSchemaOption</a>
 

 

