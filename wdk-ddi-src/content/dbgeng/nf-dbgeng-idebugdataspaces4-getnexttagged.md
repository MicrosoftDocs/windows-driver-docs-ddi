---
UID: NF:dbgeng.IDebugDataSpaces4.GetNextTagged
title: IDebugDataSpaces4::GetNextTagged method
author: windows-driver-content
description: The GetNextTagged method returns the GUID for the next block of tagged data in the enumeration.
old-location: debugger\getnexttagged.htm
old-project: debugger
ms.assetid: 529ef33a-adad-4242-96a8-01cdd273cc35
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.getnexttagged, GetNextTagged method [Windows Debugging], IDebugDataSpaces3::GetNextTagged, dbgeng/IDebugDataSpaces4::GetNextTagged, GetNextTagged method [Windows Debugging], IDebugDataSpaces3 interface, GetNextTagged, dbgeng/IDebugDataSpaces3::GetNextTagged, GetNextTagged method [Windows Debugging], IDebugDataSpaces4 interface, IDebugDataSpaces4 interface [Windows Debugging], GetNextTagged method, IDebugDataSpaces_24254a63-1fcd-4ad9-a370-6b0760ed37cd.xml, IDebugDataSpaces4, IDebugDataSpaces4::GetNextTagged, IDebugDataSpaces3 interface [Windows Debugging], GetNextTagged method
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugDataSpaces3.GetNextTagged
-	IDebugDataSpaces4.GetNextTagged
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugDataSpaces4::GetNextTagged method


## -description


The <b>GetNextTagged</b> method returns the GUID for the next block of tagged data in the enumeration.


## -syntax


````
HRESULT GetNextTagged(
  [in]  ULONG64 Handle,
  [out] LPGUID  Tag,
  [out] PULONG  Size
);
````


## -parameters




### -param Handle [in]

Specifies the handle identifying the enumeration.  This is the handle returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff558801">StartEnumTagged</a>.


### -param Tag [out]

Receives the GUID identifying the tagged data.  The data may be retrieved by passing this GUID to <a href="https://msdn.microsoft.com/library/windows/hardware/ff554336">ReadTagged</a>.


### -param Size [out]

Receives the size of the data identified by the GUID <i>Tag</i>.


## -returns


This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
There are no more blocks of tagged data available in this enumeration.

</td>
</tr>
</table> 



## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugdataspaces3.md">IDebugDataSpaces3</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558801">StartEnumTagged</a>

<a href="..\dbgeng\nn-dbgeng-idebugdataspaces4.md">IDebugDataSpaces4</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554336">ReadTagged</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugDataSpaces3::GetNextTagged method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

