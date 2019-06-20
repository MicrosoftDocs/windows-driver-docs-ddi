---
UID: NF:ntifs.ObIsKernelHandle
title: ObIsKernelHandle function (ntifs.h)
description: The ObIsKernelHandle routine determines whether the specified handle is a kernel handle.
old-location: ifsk\obiskernelhandle.htm
tech.root: ifsk
ms.assetid: 8ebc3b7f-5b4b-4e92-95fe-1918b51d27ad
ms.date: 04/16/2018
ms.keywords: ObIsKernelHandle, ObIsKernelHandle routine [Installable File System Drivers], ifsk.obiskernelhandle, ntifs/ObIsKernelHandle, obref_e80e117f-6001-4c6d-980c-413e538f3bb2.xml
ms.topic: function
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h, FltKernel.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ObIsKernelHandle
product:
- Windows
targetos: Windows
req.typenames: 
---

# ObIsKernelHandle function


## -description


The <b>ObIsKernelHandle</b> routine determines whether the specified handle is a kernel handle.


## -parameters




### -param Handle [in]

The handle to check.


## -returns



<b>ObIsKernelHandle</b> returns <b>TRUE</b> if <i>Handle</i> is a kernel handle and <b>FALSE</b> otherwise.




## -remarks



You can use kernel handles only in kernel mode.  A driver can mark a handle as a kernel handle by specifying the OBJ_KERNEL_HANDLE flag in <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a> when it creates the handle.

<div class="alert"><b>Note</b>  <b>ObIsKernelHandle</b> does not verify that the parameter is a valid handle.  This routine only determines if a valid handle is a kernel handle.  If the parameter is not a valid handle, the result of the routine is undefined.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a>
 

 

