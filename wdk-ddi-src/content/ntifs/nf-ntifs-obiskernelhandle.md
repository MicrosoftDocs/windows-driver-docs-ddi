---
UID: NF:ntifs.ObIsKernelHandle
title: ObIsKernelHandle function
author: windows-driver-content
description: The ObIsKernelHandle routine determines whether the specified handle is a kernel handle.
old-location: ifsk\obiskernelhandle.htm
old-project: ifsk
ms.assetid: 8ebc3b7f-5b4b-4e92-95fe-1918b51d27ad
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ObIsKernelHandle
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ObIsKernelHandle
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
req.typenames: TOKEN_TYPE
---

# ObIsKernelHandle function



## -description
The <b>ObIsKernelHandle</b> routine determines whether the specified handle is a kernel handle.



## -syntax

````
BOOLEAN ObIsKernelHandle(
  _In_ HANDLE Handle
);
````


## -parameters

### -param Handle [in]

The handle to check.


## -returns
<b>ObIsKernelHandle</b> returns <b>TRUE</b> if <i>Handle</i> is a kernel handle and <b>FALSE</b> otherwise.


## -remarks
You can use kernel handles only in kernel mode.  A driver can mark a handle as a kernel handle by specifying the OBJ_KERNEL_HANDLE flag in <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> when it creates the handle.


## -see-also
<dl>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20ObIsKernelHandle routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

