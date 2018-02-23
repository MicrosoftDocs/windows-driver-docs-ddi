---
UID: NF:dbgeng.IDebugClient5.OutputIdentityWide
title: IDebugClient5::OutputIdentityWide method
author: windows-driver-content
description: The OutputIdentityWide method formats and outputs a string describing the computer and user this client represents.
old-location: debugger\outputidentitywide.htm
old-project: debugger
ms.assetid: e8f91713-ea1d-4262-bc0b-dd4e39d1c2c3
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: debugger.outputidentitywide, OutputIdentityWide method [Windows Debugging], IDebugClient5 interface, IDebugClient5::OutputIdentityWide, OutputIdentityWide, IDebugClient5 interface [Windows Debugging], OutputIdentityWide method, dbgeng/IDebugClient5::OutputIdentityWide, OutputIdentityWide method [Windows Debugging], IDebugClient5
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
-	IDebugClient5.OutputIdentityWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient5::OutputIdentityWide method


## -description


The <b>OutputIdentityWide</b> method formats and outputs a string describing the computer and user this client represents.


## -syntax


````
HRESULT OutputIdentityWide(
  [in] ULONG  OutputControl,
  [in] ULONG  Flags,
  [in] PCWSTR Format
);
````


## -parameters




### -param OutputControl [in]

Specifies where to send the output.  For possible values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541517">DEBUG_OUTCTL_XXX</a>.


### -param Flags [in]

Set to zero.


### -param Format [in]

Specifies a format string similar to the <b>printf</b> format string.  However, this format string must only contain one formatting directive, <b>%s</b>, which will be replaced by a description of the computer and user this client represents.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
</table>
 




## -remarks



The specific content of the string varies with the operating system.  If the client is remotely connected, some network information may also be present.

For more information about client objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539140">Client Objects</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546831">GetIdentity</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient5::OutputIdentityWide method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

