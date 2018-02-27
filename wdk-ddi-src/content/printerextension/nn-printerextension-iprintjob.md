---
UID: NN:printerextension.IPrintJob
title: IPrintJob
author: windows-driver-content
description: Contains properties that represent a print job.
old-location: print\iprintjob.htm
old-project: print
ms.assetid: 068E53EC-26B8-48E7-A605-081709C94043
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IPrintJob, IPrintJob interface [Print Devices], IPrintJob interface [Print Devices], described, print.iprintjob, printerextension/IPrintJob
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrintJob
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintJob interface


## -description


Contains properties that represent a print job.

This interface also provides a method that allows a print job to be cancelled.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintJob</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPrintJob</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
<li><a href="https://docs.microsoft.com/">Properties</a></li>
</ul>

## -members

The <b>IPrintJob</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265404">RequestCancel</a>
</td>
<td align="left" width="63%">
Requests the cancellation of a print job.

</td>
</tr>
</table> 
<h3><a id="properties"></a>Properties</h3>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintJob</b> interface has these properties.
<table class="members" id="memberListProperties">
<tr>
<th align="left" width="27%">Property</th>
<th align="left" width="10%">Access type</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/dn895599">Id</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the print job identifier (ID).

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh971602">Name</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the name of the print job.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265403">PrintedPages</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the number of pages that have been printed.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265407">Status</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the current status of the print job.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265410">SubmissionTime</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the submission time, in the “DATE” format, provided in the user’s local time (not in the UTC format that is provided by the spooler).

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265411">TotalPages</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the total number of pages that the document contains.

</td>
</tr>
</table> 


## -remarks



The <b>IPrintJob</b> interface provides a wrapper around select properties of the spooler’s <a href="http://msdn.microsoft.com/en-us/library/windows/desktop/dd145019(v=vs.85).aspx">JOB_INFO_1</a> structure.

<b>IPrintJob</b> also helps to make it possible to perform job management from a UWP device app or from a printer extension. For more information, see <a href="https://msdn.microsoft.com/D1236DD2-D4AD-4615-9036-7EC75D6CADCE">Job Management</a>.




## -see-also

<a href="https://msdn.microsoft.com/D1236DD2-D4AD-4615-9036-7EC75D6CADCE">Job Management</a>



<a href="http://msdn.microsoft.com/en-us/library/windows/desktop/dd145019(v=vs.85).aspx">JOB_INFO_1</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintJob interface%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

