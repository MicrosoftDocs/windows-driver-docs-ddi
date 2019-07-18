---
UID: NN:dbgeng.IDebugDataSpaces3
title: IDebugDataSpaces3 (dbgeng.h)
description: IDebugDataSpaces3 interface
old-location: debugger\idebugdataspaces3.htm
tech.root: debugger
ms.assetid: a5da1ed0-c4e6-4ab8-b581-64bc7d0519f2
ms.date: 05/03/2018
ms.keywords: IDebugDataSpaces3, IDebugDataSpaces3 interface [Windows Debugging], IDebugDataSpaces3 interface [Windows Debugging],described, dbgeng/IDebugDataSpaces3, debugger.idebugdataspaces3
ms.topic: interface
f1_keywords:
 - "dbgeng/IDebugDataSpaces3"
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
- IDebugDataSpaces3
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugDataSpaces3 interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugDataSpaces3</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugdataspaces2">IDebugDataSpaces2</a>. <b>IDebugDataSpaces3</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugDataSpaces3</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-endenumtagged">EndEnumTagged</a>
</td>
<td align="left" width="63%">
Releases the resources used by the specified enumeration.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-getnexttagged">GetNextTagged</a>
</td>
<td align="left" width="63%">
Returns the GUID for the next block of tagged data in the enumeration.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-readimagentheaders">ReadImageNtHeaders</a>
</td>
<td align="left" width="63%">
Returns the NT headers for the specified image loaded in the target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-readtagged">ReadTagged</a>
</td>
<td align="left" width="63%">
Reads the tagged data that might be associated with a debugger session.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-startenumtagged">StartEnumTagged</a>
</td>
<td align="left" width="63%">
Initializes a enumeration over the tagged data associated with a debugger session.


</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugdataspaces">IDebugDataSpaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugdataspaces2">IDebugDataSpaces2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugdataspaces4">IDebugDataSpaces4</a>
 

 

