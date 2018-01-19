---
UID: NF:dbgeng.IDebugDataSpaces4.GetNextTagged
title: IDebugDataSpaces4::GetNextTagged method
author: windows-driver-content
description: The GetNextTagged method returns the GUID for the next block of tagged data in the enumeration.
old-location: debugger\getnexttagged.htm
old-project: debugger
ms.assetid: 529ef33a-adad-4242-96a8-01cdd273cc35
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugDataSpaces4, IDebugDataSpaces4::GetNextTagged, GetNextTagged
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
req.alt-api: IDebugDataSpaces3.GetNextTagged,IDebugDataSpaces4.GetNextTagged
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
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
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>S_FALSE</b></dt>
</dl>There are no more blocks of tagged data available in this enumeration.

 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces3.md">IDebugDataSpaces3</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces4.md">IDebugDataSpaces4</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558801">StartEnumTagged</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554336">ReadTagged</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugDataSpaces3::GetNextTagged method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

