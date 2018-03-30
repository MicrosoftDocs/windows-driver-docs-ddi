---
UID: NF:dbgeng.IDebugControl4.GetManagedStatusWide
title: IDebugControl4::GetManagedStatusWide method
author: windows-driver-content
description: Provides feedback as a Unicode character string on the engine's use of the runtime debugging APIs provided by the common language runtime (CLR).
old-location: debugger\idebugcontrol4_getmanagedstatuswide.htm
old-project: debugger
ms.assetid: 5854BB6A-EB5F-493A-96E4-0DF298EC0332
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetManagedStatusWide method [Windows Debugging], GetManagedStatusWide method [Windows Debugging], IDebugControl4 interface, GetManagedStatusWide,IDebugControl4.GetManagedStatusWide, IDebugControl4, IDebugControl4 interface [Windows Debugging], GetManagedStatusWide method, IDebugControl4::GetManagedStatusWide, dbgeng/IDebugControl4::GetManagedStatusWide, debugger.idebugcontrol4_getmanagedstatuswide
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugControl4.GetManagedStatusWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl4::GetManagedStatusWide method


## -description


 Provides feedback as a Unicode character string on the engine's
    use of the runtime debugging APIs provided by the common language runtime (CLR).


## -parameters




### -param Flags [out, optional]

A pointer to flags from the debugging APIs.


### -param WhichString [in]

A value that controls which string to use.


### -param String [out]

A pointer to a Unicode character string from the debugging APIs.


### -param StringSize [in]

The size of the string.


### -param StringNeeded [out, optional]

A pointer to an output string.


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
 

    Managed debugging support relies on debugging
    functionality provided by the CLR.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550526">IDebugControl4</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::GetManagedStatusWide method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
