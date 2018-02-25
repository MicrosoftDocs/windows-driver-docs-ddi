---
UID: NF:miniport.WRITE_REGISTER_BUFFER_USHORT
title: WRITE_REGISTER_BUFFER_USHORT function
author: windows-driver-content
description: The WRITE_REGISTER_BUFFER_USHORT routine writes a number of USHORT values from a buffer to the specified register.
old-location: kernel\write_register_buffer_ushort.htm
old-project: kernel
ms.assetid: 070fc2b0-045e-4778-82d4-0850cd2064a5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , B, E, F, G, H, I, O, R, S, T, U, W, WRITE_REGISTER_BUFFER_USHORT, WRITE_REGISTER_BUFFER_USHORT routine [Kernel-Mode Driver Architecture], _, k103_31475540-7ba8-44b6-ad54-e794ffddf8ee.xml, kernel.write_register_buffer_ushort, wdm/WRITE_REGISTER_BUFFER_USHORT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	WRITE_REGISTER_BUFFER_USHORT
product: Windows
targetos: Windows
req.typenames: MEMORY_CACHING_TYPE
---

# WRITE_REGISTER_BUFFER_USHORT function


## -description


The <b>WRITE_REGISTER_BUFFER_USHORT</b> routine writes a number of USHORT values from a buffer to the specified register. 


## -syntax


````
VOID WRITE_REGISTER_BUFFER_USHORT(
  _In_ PUSHORT Register,
  _In_ PUSHORT Buffer,
  _In_ ULONG   Count
);
````


## -parameters




### -param Register [in]

Pointer to the register, which must be a mapped range in memory space.


### -param Buffer [in]

Pointer to a buffer from which an array of USHORT values is to be written.


### -param Count [in]

Specifies the number of USHORT values to be written to the register. 


## -returns



None




## -remarks



The size of the buffer must be large enough to contain at least the specified number of USHORT values.

Callers of <b>WRITE_REGISTER_BUFFER_USHORT</b> can be running at any IRQL, assuming the <i>Buffer</i> is resident and the <i>Register</i> is resident, mapped device memory.



