---
UID: NF:wdm.IoSetShareAccessEx
title: IoSetShareAccessEx function (wdm.h)
description: The IoSetShareAccessEx routine sets the access rights for sharing the specified file object.
old-location: kernel\iosetshareaccessex.htm
tech.root: kernel
ms.assetid: 4DCC4A37-0099-4C6F-B00D-B6CAA7D1EC68
ms.date: 04/30/2018
keywords: ["IoSetShareAccessEx function"]
ms.keywords: IoSetShareAccessEx, IoSetShareAccessEx routine [Kernel-Mode Driver Architecture], kernel.iosetshareaccessex, wdm/IoSetShareAccessEx
f1_keywords:
 - "wdm/IoSetShareAccessEx"
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ntoskrnl.lib
- ntoskrnl.dll
api_name:
- IoSetShareAccessEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoSetShareAccessEx function


## -description


The <b>IoSetShareAccessEx</b> routine sets the access rights for sharing the specified file object.


## -parameters




### -param DesiredAccess [in]

Specifies an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> value that represents the type of access requested for the file object. See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatefile">IoCreateFile</a> for a complete list of system-defined <i>DesiredAccess</i> flags.


### -param DesiredShareAccess [in]

Specifies the type of share access to be set for the file object. This value can be zero, or any combination of the following flags:

FILE_SHARE_READ

FILE_SHARE_WRITE

FILE_SHARE_DELETE


### -param FileObject [in, out]

A pointer to the file object whose share access is being set or reset.


### -param ShareAccess [out]

A pointer to the <b>SHARE_ACCESS</b> structure that is associated with <i>FileObject</i>. Drivers should treat this structure as opaque.


### -param WritePermission [in, optional]

A pointer to the value that specifies whether the file object has write permission. This value is <b>TRUE</b> if the share has write permission; otherwise, it is <b>FALSE</b>. If  the value is <b>FALSE</b>  and the caller attempts to take exclusive read access, the write permission is downgraded to FILE_SHARE_READ.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatefile">IoCreateFile</a>
 

 

