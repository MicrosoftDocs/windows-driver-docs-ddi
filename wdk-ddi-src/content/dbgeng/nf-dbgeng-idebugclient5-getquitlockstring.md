---
UID: NF:dbgeng.IDebugClient5.GetQuitLockString
title: IDebugClient5::GetQuitLockString method
author: windows-driver-content
description: Gets a quit lock string.
old-location: debugger\idebugclient5_getquitlockstring.htm
old-project: debugger
ms.assetid: 986C866E-D5AC-47CD-A666-EDF739E91761
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.idebugclient5_getquitlockstring, GetQuitLockString method [Windows Debugging], GetQuitLockString, GetQuitLockString method [Windows Debugging], IDebugClient5 interface, IDebugClient5, dbgeng/IDebugClient5::GetQuitLockString, IDebugClient5::GetQuitLockString, IDebugClient5 interface [Windows Debugging], GetQuitLockString method
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
-	IDebugClient5.GetQuitLockString
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugClient5::GetQuitLockString method


## -description


Gets a quit lock string.


## -syntax


````
HRESULT GetQuitLockString(
  [out]           writes_opt_(BufferSize) PSTR Buffer,
  [in]            ULONG                        BufferSize,
  [out, optional] PULONG                       StringSize
);
````


## -parameters




### -param Buffer [out]

The buffer in which to write the string.


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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient5::GetQuitLockString method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

