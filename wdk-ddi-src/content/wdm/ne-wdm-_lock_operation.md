---
UID: NE:wdm._LOCK_OPERATION
title: "_LOCK_OPERATION"
author: windows-driver-content
description: The LOCK_OPERATION enumeration specifies the type of access that is appropriate for a type of I/O operation.
old-location: ifsk\lock_operation.htm
tech.root: ifsk
ms.assetid: 25b2dd6a-2e20-4221-bef4-0001bbaae1d5
ms.date: 04/16/2018
ms.keywords: IoModifyAccess, IoReadAccess, IoWriteAccess, LOCK_OPERATION, LOCK_OPERATION enumeration [Installable File System Drivers], _LOCK_OPERATION, ifsk.lock_operation, wdm/IoModifyAccess, wdm/IoReadAccess, wdm/IoWriteAccess, wdm/LOCK_OPERATION
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating system.
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
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	LOCK_OPERATION
product:
- Windows
targetos: Windows
req.typenames: LOCK_OPERATION
---

# _LOCK_OPERATION enumeration


## -description


The <b>LOCK_OPERATION</b> enumeration specifies the type of access that is appropriate for a type of I/O operation.


## -enum-fields




### -field IoReadAccess

This value indicates that a driver  can examine the contents of a buffer but cannot change the contents.


### -field IoWriteAccess

This value indicates that a driver can examine and change the contents of a buffer. 


### -field IoModifyAccess

This value indicates that a driver can examine and change the contents of a buffer.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541956">FltDecodeParameters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554664">MmProbeAndLockPages</a>
 

 

