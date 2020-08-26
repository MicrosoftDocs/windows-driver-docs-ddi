---
UID: NF:wdm.WRITE_REGISTER_BUFFER_UCHAR
title: WRITE_REGISTER_BUFFER_UCHAR function (wdm.h)
description: The WRITE_REGISTER_BUFFER_UCHAR routine writes a number of bytes from a buffer to the specified register.
old-location: kernel\write_register_buffer_uchar.htm
tech.root: kernel
ms.assetid: 4cb90f37-c7ce-4f78-9e68-cbe4aaf6ea72
ms.date: 04/30/2018
keywords: ["WRITE_REGISTER_BUFFER_UCHAR function"]
ms.keywords: WRITE_REGISTER_BUFFER_UCHAR, WRITE_REGISTER_BUFFER_UCHAR routine [Kernel-Mode Driver Architecture], k103_29b68153-db95-4017-ab96-d05e6c984503.xml, kernel.write_register_buffer_uchar, wdm/WRITE_REGISTER_BUFFER_UCHAR
f1_keywords:
 - "wdm/WRITE_REGISTER_BUFFER_UCHAR"
 - "WRITE_REGISTER_BUFFER_UCHAR"
req.header: wdm.h
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
- WRITE_REGISTER_BUFFER_UCHAR
targetos: Windows
req.typenames: 
---

# WRITE_REGISTER_BUFFER_UCHAR function


## -description


The <b>WRITE_REGISTER_BUFFER_UCHAR</b> routine writes a number of bytes from a buffer to the specified register.


## -parameters




### -param Register 
[in]
Pointer to the register, which must be a mapped range in memory space.


### -param Buffer 
[in]
Pointer to a buffer from which an array of UCHAR values is to be written.


### -param Count 
[in]
Specifies the number of bytes to be written to the register. 


## -remarks



The size of the buffer must be large enough to contain at least the specified number of bytes.

Callers of <b>WRITE_REGISTER_BUFFER_UCHAR</b> can be running at any IRQL, assuming the <i>Buffer</i> is resident and the <i>Register</i> is resident, mapped device memory.



