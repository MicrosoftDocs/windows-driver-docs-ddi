---
UID: NF:dbgeng.IDebugClient5.GetQuitLockStringWide
title: IDebugClient5::GetQuitLockStringWide method
author: windows-driver-content
description: Gets a Unicode character quit lock string.
old-location: debugger\idebugclient5_getquitlockstringwide.htm
old-project: debugger
ms.assetid: 0C69F19C-D048-47EB-9286-6F8C6E3398CC
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetQuitLockStringWide method [Windows Debugging], GetQuitLockStringWide method [Windows Debugging], IDebugClient5 interface, GetQuitLockStringWide,IDebugClient5.GetQuitLockStringWide, IDebugClient5, IDebugClient5 interface [Windows Debugging], GetQuitLockStringWide method, IDebugClient5::GetQuitLockStringWide, dbgeng/IDebugClient5::GetQuitLockStringWide, debugger.idebugclient5_getquitlockstringwide
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
-	IDebugClient5.GetQuitLockStringWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient5::GetQuitLockStringWide method


## -description


Gets a Unicode character quit lock string.


## -syntax


````
HRESULT GetQuitLockStringWide(
  [out]           writes_opt_(BufferSize) PWSTR Buffer,
  [in]            ULONG                         BufferSize,
  [out, optional] PULONG                        StringSize
);
````


## -parameters




### -param Buffer [out]

The buffer in which to write the Unicode character string.


### -param BufferSize [in]

The size of the buffer.


### -param StringSize [out, optional]

A pointer to the string size.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



    A quit lock string provides control to lock the session against
    undesired quits.  

The quit lock string
    cannot be retrieved from a secure session.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient5::GetQuitLockStringWide method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

