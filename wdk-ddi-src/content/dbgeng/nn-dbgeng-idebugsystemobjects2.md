---
UID: NN:dbgeng.IDebugSystemObjects2
title: IDebugSystemObjects2
author: windows-driver-content
description: IDebugSystemObjects2 interface
old-location: debugger\idebugsystemobjects2.htm
old-project: debugger
ms.assetid: 9e354357-590b-45cf-bace-5b431f408422
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IDebugSystemObjects2, IDebugSystemObjects2 interface [Windows Debugging], IDebugSystemObjects2 interface [Windows Debugging], described, dbgeng/IDebugSystemObjects2, debugger.idebugsystemobjects2
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
-	IDebugSystemObjects2
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSystemObjects2 interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugSystemObjects2</b> interface inherits from <a href="..\dbgeng\nn-dbgeng-idebugsystemobjects.md">IDebugSystemObjects</a>. <b>IDebugSystemObjects2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugSystemObjects2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545857">GetCurrentProcessUpTime</a>
</td>
<td align="left" width="63%">
Returns the length of time the current process has been running.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546865">GetImplicitProcessDataOffset</a>
</td>
<td align="left" width="63%">
Returns the implicit process for the current target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546871">GetImplicitThreadDataOffset</a>
</td>
<td align="left" width="63%">
Returns the implicit thread for the current process.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556713">SetImplicitProcessDataOffset</a>
</td>
<td align="left" width="63%">
Sets the implicit process for the current target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556716">SetImplicitThreadDataOffset</a>
</td>
<td align="left" width="63%">
Sets the implicit thread for the current process.

</td>
</tr>
</table> 


## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugsystemobjects.md">IDebugSystemObjects</a>



<a href="..\dbgeng\nn-dbgeng-idebugsystemobjects3.md">IDebugSystemObjects3</a>



<a href="..\dbgeng\nn-dbgeng-idebugsystemobjects4.md">IDebugSystemObjects4</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSystemObjects2 interface%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

