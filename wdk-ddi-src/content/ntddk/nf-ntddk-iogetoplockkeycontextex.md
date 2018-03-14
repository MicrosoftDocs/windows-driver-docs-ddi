---
UID: NF:ntddk.IoGetOplockKeyContextEx
title: IoGetOplockKeyContextEx function
author: windows-driver-content
description: The IoGetOplockKeyContextEx routine returns a parent and target oplock key context for a file object.
old-location: ifsk\iogetoplockkeycontextex.htm
old-project: ifsk
ms.assetid: 2DFC2C13-19C4-4DFD-B18B-459B38521962
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IoGetOplockKeyContextEx, IoGetOplockKeyContextEx routine [Installable File System Drivers], ifsk.iogetoplockkeycontextex, ntddk/IoGetOplockKeyContextEx
ms.prod: windows-hardware
ms.technology: windows-devices
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
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoGetOplockKeyContextEx function


## -description


The <b>IoGetOplockKeyContextEx</b> routine returns a parent and target oplock key context for a file object.


## -syntax


````
POPLOCK_KEY_CONTEXT IoGetOplockKeyContextEx(
   PFILE_OBJECT FileObject
);
````


## -parameters




### -param FileObject

The file object to query for an oplock key context.


## -returns



An pointer to an <a href="..\ntddk\ns-ntddk-_oplock_key_context.md">OPLOCK_KEY_CONTEXT</a> structure containing the oplock keys for <i>FileObject</i>. Otherwise, NULL if <i>FileObject</i>  has no  oplock keys.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551003">OPLOCK_KEY_ECP_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406392">DUAL_OPLOCK_KEY_ECP_CONTEXT</a>



<a href="..\ntddk\ns-ntddk-_oplock_key_context.md">OPLOCK_KEY_CONTEXT</a>



 

 


