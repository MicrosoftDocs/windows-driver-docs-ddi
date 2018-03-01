---
UID: NN:dbgeng.IDebugDataSpaces3
title: IDebugDataSpaces3
author: windows-driver-content
description: IDebugDataSpaces3 interface
old-location: debugger\idebugdataspaces3.htm
old-project: debugger
ms.assetid: a5da1ed0-c4e6-4ab8-b581-64bc7d0519f2
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugDataSpaces3, IDebugDataSpaces3 interface [Windows Debugging], IDebugDataSpaces3 interface [Windows Debugging], described, dbgeng/IDebugDataSpaces3, debugger.idebugdataspaces3
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugDataSpaces3
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugDataSpaces3 interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugDataSpaces3</b> interface inherits from <a href="..\dbgeng\nn-dbgeng-idebugdataspaces2.md">IDebugDataSpaces2</a>. <b>IDebugDataSpaces3</b> also has these types of members:
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542978">EndEnumTagged</a>
</td>
<td align="left" width="63%">
Releases the resources used by the specified enumeration.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547874">GetNextTagged</a>
</td>
<td align="left" width="63%">
Returns the GUID for the next block of tagged data in the enumeration.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553544">ReadImageNtHeaders</a>
</td>
<td align="left" width="63%">
Returns the NT headers for the specified image loaded in the target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554336">ReadTagged</a>
</td>
<td align="left" width="63%">
Reads the tagged data that might be associated with a debugger session.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558801">StartEnumTagged</a>
</td>
<td align="left" width="63%">
Initializes a enumeration over the tagged data associated with a debugger session.


</td>
</tr>
</table> 


## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugdataspaces4.md">IDebugDataSpaces4</a>



<a href="..\dbgeng\nn-dbgeng-idebugdataspaces2.md">IDebugDataSpaces2</a>



<a href="..\dbgeng\nn-dbgeng-idebugdataspaces.md">IDebugDataSpaces</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugDataSpaces3 interface%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

