---
UID: NF:dbgeng.IDebugSystemObjects3.GetCurrentSystemServerName
title: IDebugSystemObjects3::GetCurrentSystemServerName method
author: windows-driver-content
description: Gets the server name for the current process.
old-location: debugger\idebugsystemobjects3_getcurrentsystemservername.htm
old-project: debugger
ms.assetid: 4E06AFD0-42D3-479F-B285-34919826F750
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects3, IDebugSystemObjects3::GetCurrentSystemServerName, GetCurrentSystemServerName
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
req.alt-api: IDebugSystemObjects3.GetCurrentSystemServerName
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

# IDebugSystemObjects3::GetCurrentSystemServerName method



## -description
Gets the server name for the current process.



## -syntax

````
HRESULT GetCurrentSystemServerName(
  [out]           _writes_opt_(BufferSize) PSTR Buffer,
  [in]            ULONG                         BufferSize,
  [out, optional] PULONG                        NameSize
);
````


## -parameters

### -param Buffer [out]

A pointer to an output buffer.


### -param BufferSize [in]

The size of the buffer.


### -param NameSize [out, optional]

A pointer to the name size. 


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541386">Debugging Session and Execution Model</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsystemobjects3.md">IDebugSystemObjects3</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSystemObjects3::GetCurrentSystemServerName method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

