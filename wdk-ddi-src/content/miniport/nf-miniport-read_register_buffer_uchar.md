---
UID: NF:miniport.READ_REGISTER_BUFFER_UCHAR
title: READ_REGISTER_BUFFER_UCHAR function (miniport.h)
description: The READ_REGISTER_BUFFER_UCHAR routine reads a number of bytes from the specified register address into a buffer.
old-location: kernel\read_register_buffer_uchar.htm
tech.root: kernel
ms.assetid: 4ce9f377-ca5e-4574-9d80-60b74ee0de85
ms.date: 04/30/2018
keywords: ["READ_REGISTER_BUFFER_UCHAR function"]
ms.keywords: READ_REGISTER_BUFFER_UCHAR, READ_REGISTER_BUFFER_UCHAR routine [Kernel-Mode Driver Architecture], k103_053aab44-4a1f-4eb3-a052-ee00f16a349d.xml, kernel.read_register_buffer_uchar, wdm/READ_REGISTER_BUFFER_UCHAR
f1_keywords:
 - "miniport/READ_REGISTER_BUFFER_UCHAR"
 - "READ_REGISTER_BUFFER_UCHAR"
req.header: miniport.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h, Wudfwdm.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: Any level (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- READ_REGISTER_BUFFER_UCHAR
targetos: Windows
req.typenames: 
---

# READ_REGISTER_BUFFER_UCHAR function


## -description


The <b>READ_REGISTER_BUFFER_UCHAR</b> routine reads a number of bytes from the specified register address into a buffer. 


## -parameters




### -param Register [in]

Pointer to the register, which must be a mapped range in memory space.


### -param Buffer [out]

Pointer to a buffer into which an array of UCHAR values is read. 


### -param Count [in]

Specifies the number of bytes to be read into the buffer. 


## -remarks



The size of the buffer must be large enough to contain at least the specified number of bytes.

Callers of <b>READ_REGISTER_BUFFER_UCHAR</b> can be running at any IRQL, assuming the <i>Buffer</i> is resident and the <i>Register</i> is resident, mapped device memory.



