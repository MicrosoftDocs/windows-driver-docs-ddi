---
UID: NF:ntddk.IoGetOplockKeyContextEx
title: IoGetOplockKeyContextEx function (ntddk.h)
description: The IoGetOplockKeyContextEx routine returns a dual oplock key context for a file object.
old-location: ifsk\iogetoplockkeycontext.htm
tech.root: ifsk
ms.assetid: E93091A2-203B-418D-93E7-1219DED25C52
ms.date: 04/16/2018
ms.keywords: IoGetOplockKeyContext, IoGetOplockKeyContextEx, IoGetOplockKeyContextEx routine [Installable File System Drivers], ifsk.iogetoplockkeycontext, ntddk/IoGetOplockKeyContextEx
ms.topic: function
req.header: ntddk.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: The IoGetOplockKeyContextEx routine is available starting with Windows 8.
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
req.lib: Ntoskrnl.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ntoskrnl.lib
-	ntoskrnl.dll
api_name:
-	IoGetOplockKeyContextEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoGetOplockKeyContextEx function


## -description


The <b>IoGetOplockKeyContext</b> routine returns a dual oplock key context for a file object.


## -parameters




### -param FileObject

The file object to query for an oplock key context.


## -returns



An pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh439448">OPLOCK_KEY_CONTEXT</a> structure containing the parent and target oplock keys for <i>FileObject</i>. Otherwise, NULL if <i>FileObject</i> has no oplock keys.




## -remarks



On Windows 8 and later versions of Windows, use <b>IoGetOplockKeyContextEx</b> instead of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-iogetoplockkeycontext">IoGetOplockKeyContext</a>, as the latter only returns a target oplock key context.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406392">DUAL_OPLOCK_KEY_ECP_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439325">IoGetOplockKeyContextEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439448">OPLOCK_KEY_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551003">OPLOCK_KEY_ECP_CONTEXT</a>
 

 

