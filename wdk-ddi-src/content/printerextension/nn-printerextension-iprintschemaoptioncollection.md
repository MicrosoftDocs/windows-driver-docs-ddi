---
UID: NN:printerextension.IPrintSchemaOptionCollection
title: IPrintSchemaOptionCollection
author: windows-driver-content
description: Exposes a collection of IPrintSchemaOption objects.
old-location: print\iprintschemaoptioncollection.htm
old-project: print
ms.assetid: ED0FD042-EB42-4F4B-AF9C-B8F56909ED66
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: print.iprintschemaoptioncollection, IPrintSchemaOptionCollection interface [Print Devices], IPrintSchemaOptionCollection interface [Print Devices], described, IPrintSchemaOptionCollection, printerextension/IPrintSchemaOptionCollection
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
-	IPrintSchemaOptionCollection
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaOptionCollection interface


## -description


Exposes a collection of <a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a> objects.


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
Gets a pointer to an <a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a> object.

</td>
</tr>
</table>Gets a pointer to an <a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a> object.

 

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaOptionCollection</b> interface has these properties.
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
Gets a count of the number of <a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a> objects in the collection.

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
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406342">Count</a>


Read-only

Gets a count of the number of <a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a> objects in the collection.


<a href="https://msdn.microsoft.com/library/windows/hardware/hh973226">NewEnum</a>


Read-only

Gets a pointer to the enumerants of <b>IPrintSchemaOptionCollection</b> objects.

 


## -see-also

<a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a>

<a href="https://msdn.microsoft.com/ebbff4bc-36b2-4861-9efa-ffa45e013eb5">IDispatch</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaOptionCollection interface%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

