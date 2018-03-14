---
UID: NF:ntddk.IoGetOplockKeyContext
title: IoGetOplockKeyContext function
author: windows-driver-content
description: The IoGetOplockKeyContext routine returns a target oplock key context for a file object.
old-location: ifsk\iogetoplockkeycontext.htm
old-project: ifsk
ms.assetid: E93091A2-203B-418D-93E7-1219DED25C52
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IoGetOplockKeyContext, IoGetOplockKeyContextEx, IoGetOplockKeyContextEx routine [Installable File System Drivers], ifsk.iogetoplockkeycontext, ntddk/IoGetOplockKeyContextEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: The IoGetOplockKeyContext routine is available starting with Windows 7.
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
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoGetOplockKeyContext function


## -description


The <b>IoGetOplockKeyContext</b> routine returns a target oplock key context for a file object.


## -syntax


````
POPLOCK_KEY_ECP_CONTEXT IoGetOplockKeyContextEx(
   PFILE_OBJECT FileObject
);
````


## -parameters




### -param FileObject

The file object to query for an oplock key context.


## -returns



An pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551003">OPLOCK_KEY_ECP_CONTEXT</a> structure containing the target oplock key for <i>FileObject</i>. Otherwise, NULL if <i>FileObject</i>  has no target oplock key.




## -remarks



Use the <b>IoGetOplockKeyContext</b> routine only in Windows 7. Because  <a href="..\ntddk\nf-ntddk-iogetoplockkeycontextex.md">IoGetOplockKeyContextEx</a> returns a dual oplock key context, it should be used in Windows 8 and later versions of Windows.




## -see-also

<a href="..\ntddk\nf-ntddk-iogetoplockkeycontextex.md">IoGetOplockKeyContextEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551003">OPLOCK_KEY_ECP_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406392">DUAL_OPLOCK_KEY_ECP_CONTEXT</a>



<a href="..\ntddk\ns-ntddk-_oplock_key_context.md">OPLOCK_KEY_CONTEXT</a>



 

 


