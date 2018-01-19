---
UID: NF:dbgeng.IDebugSymbols3.AppendImagePathWide
title: IDebugSymbols3::AppendImagePathWide method
author: windows-driver-content
description: The AppendImagePathWide method appends directories to the executable image path.
old-location: debugger\appendimagepathwide.htm
old-project: debugger
ms.assetid: 9a129ce5-4493-4838-9a6c-8a3c054e7c27
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSymbols3, IDebugSymbols3::AppendImagePathWide, AppendImagePathWide
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
req.alt-api: IDebugSymbols3.AppendImagePathWide
req.alt-loc: Dbgeng.h
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

# IDebugSymbols3::AppendImagePathWide method



## -description
The <b>AppendImagePathWide</b>  method appends directories to the executable image path.



## -syntax

````
HRESULT AppendImagePathWide(
  [in] PCSTR Addition
);
````


## -parameters

### -param Addition [in]

Specifies the directories to append to the executable image path.  This is a string that contains directory names separated by semicolons (;).


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.


## -remarks
The executable image path is used by the <a href="debugger.e#engine#engine"><i>engine</i></a> when searching for executable images.

The executable image path can consist of several directories separated by semicolons (;).  These directories are searched in order.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546851">GetImagePath</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556708">SetImagePath</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::AppendImagePathWide method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

