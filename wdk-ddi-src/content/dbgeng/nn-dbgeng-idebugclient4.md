---
UID: NN:dbgeng.IDebugClient4
title: IDebugClient4 (dbgeng.h)
description: IDebugClient4 interface
old-location: debugger\idebugclient4.htm
tech.root: debugger
ms.assetid: fcfa64f3-6cdf-4e5a-bb02-13a748fd6dda
ms.date: 05/03/2018
ms.keywords: IDebugClient4, IDebugClient4 interface [Windows Debugging], IDebugClient4 interface [Windows Debugging],described, dbgeng/IDebugClient4, debugger.idebugclient4
ms.topic: interface
f1_keywords:
 - "dbgeng/IDebugClient4"
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
- dbgeng.h
api_name:
- IDebugClient4
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient4 interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugClient4</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>. <b>IDebugClient4</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugClient4</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-adddumpinformationfilewide">AddDumpInformationFileWide</a>
</td>
<td align="left" width="63%">
Registers additional files containing supporting information that will be used when opening a dump file.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getdumpfile">GetDumpFile</a>
</td>
<td align="left" width="63%">
Describes the files containing supporting information that were used when opening the current dump target.
(ANSI version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getdumpfilewide">GetDumpFileWide</a>
</td>
<td align="left" width="63%">
Describes the files containing supporting information that were used when opening the current dump target.
(Unicode version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getnumberdumpfiles">GetNumberDumpFiles</a>
</td>
<td align="left" width="63%">
Returns the number of files containing supporting information that were used when opening the current dump target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-opendumpfilewide">OpenDumpFileWide</a>
</td>
<td align="left" width="63%">
Opens a dump file as a debugger target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-writedumpfilewide">WriteDumpFileWide</a>
</td>
<td align="left" width="63%">
Creates a user-mode or kernel-mode crash dump file.


</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>
 

 

