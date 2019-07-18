---
UID: NN:printerextension.IPrintJob
title: IPrintJob (printerextension.h)
description: Contains properties that represent a print job.
old-location: print\iprintjob.htm
tech.root: print
ms.assetid: 068E53EC-26B8-48E7-A605-081709C94043
ms.date: 04/20/2018
ms.keywords: IPrintJob, IPrintJob interface [Print Devices], IPrintJob interface [Print Devices],described, print.iprintjob, printerextension/IPrintJob
ms.topic: interface
f1_keywords:
 - "printerextension/IPrintJob"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Printerextension.h
api_name:
- IPrintJob
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintJob interface


## -description


Contains properties that represent a print job.

This interface also provides a method that allows a print job to be cancelled.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintJob</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPrintJob</b> also has these types of members:
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
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintjob-requestcancel">RequestCancel</a>
</td>
<td align="left" width="63%">
Requests the cancellation of a print job.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintjob-get_status">Status</a>
</td>
<td align="left" width="63%">
Gets the current status of the print job.

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

<a href="https://docs.microsoft.com/windows-hardware/customize/desktop/unattend/microsoft-windows-shwebsvc-id">Id</a>


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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschemaelement-get_name">Name</a>


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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintjob-get_printedpages">PrintedPages</a>


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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintjob-get_submissiontime">SubmissionTime</a>


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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintjob-get_totalpages">TotalPages</a>


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



The <b>IPrintJob</b> interface provides a wrapper around select properties of the spooler’s <a href="https://docs.microsoft.com/windows/desktop/printdocs/job-info-1">JOB_INFO_1</a> structure.

<b>IPrintJob</b> also helps to make it possible to perform job management from a UWP device app or from a printer extension. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/job-management">Job Management</a>.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/printdocs/job-info-1">JOB_INFO_1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/job-management">Job Management</a>
 

 

