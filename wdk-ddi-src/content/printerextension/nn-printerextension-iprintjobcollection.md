---
UID: NN:printerextension.IPrintJobCollection
title: IPrintJobCollection
author: windows-driver-content
description: This interfaces provides an enumeration of the jobs in the print queue.
old-location: print\iprintjobcollection.htm
old-project: print
ms.assetid: 757328A6-DD2C-4057-820B-39EB83277194
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: print.iprintjobcollection, IPrintJobCollection interface [Print Devices], IPrintJobCollection interface [Print Devices], described, IPrintJobCollection, printerextension/IPrintJobCollection
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	IPrintJobCollection
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintJobCollection interface


## -description


This interfaces provides an enumeration of the jobs in the print queue.

The enumerated list of jobs represents a snapshot of the current job status.


## -members

The <b>IPrintJobCollection</b> interface has these methods.
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
Gets a pointer to an <a href="..\printerextension\nn-printerextension-iprintjob.md">IPrintJob</a> object.

</td>
</tr>
</table>Gets a pointer to an <a href="..\printerextension\nn-printerextension-iprintjob.md">IPrintJob</a> object.

 

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintJobCollection</b> interface has these properties.
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
Gets the number of jobs in the print queue.

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
Gets a pointer to the enumerants of <b>IPrintJobCollection</b> objects.

</td>
</tr>
</table>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406342">Count</a>


Read-only

Gets the number of jobs in the print queue.


<a href="https://msdn.microsoft.com/library/windows/hardware/hh973226">NewEnum</a>


Read-only

Gets a pointer to the enumerants of <b>IPrintJobCollection</b> objects.

 


## -remarks


The order of print jobs in the enumerated list is the same as the order provided by <a href="http://msdn.microsoft.com/en-us/library/windows/desktop/dd162625(v=vs.85).aspx">EnumJobs</a>, which is the actual print queue order.

<b>IPrintJobCollection</b> also helps to make it possible to perform job management from a UWP device app or from a printer extension. For more information, see <a href="https://msdn.microsoft.com/D1236DD2-D4AD-4615-9036-7EC75D6CADCE">Job Management</a>.



## -see-also

<a href="http://msdn.microsoft.com/en-us/library/windows/desktop/dd162625(v=vs.85).aspx">EnumJobs</a>

<a href="https://msdn.microsoft.com/D1236DD2-D4AD-4615-9036-7EC75D6CADCE">Job Management</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintJobCollection interface%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

