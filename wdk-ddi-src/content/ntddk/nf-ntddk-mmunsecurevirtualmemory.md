---
UID: NF:ntddk.MmUnsecureVirtualMemory
title: MmUnsecureVirtualMemory function
description: The MmUnsecureVirtualMemory routine unsecures a memory address range secured by the MmSecureVirtualMemory routine.
old-location: kernel\mmunsecurevirtualmemory.htm
tech.root: kernel
ms.assetid: 979eef24-e53b-476c-b9db-e56c43630913
ms.date: 04/30/2018
ms.keywords: MmUnsecureVirtualMemory, MmUnsecureVirtualMemory routine [Kernel-Mode Driver Architecture], k106_0bfc6e9e-a4e9-4868-b1fb-da6714146dbf.xml, kernel.mmunsecurevirtualmemory, ntddk/MmUnsecureVirtualMemory
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows. This routine is not available in Windows 98/Me.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlMmApcLte, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<=APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	MmUnsecureVirtualMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# MmUnsecureVirtualMemory function


## -description


The <b>MmUnsecureVirtualMemory</b> routine unsecures a memory address range secured by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556374">MmSecureVirtualMemory</a> routine. 


## -parameters




### -param SecureHandle [in]

Specifies the value returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff556374">MmSecureVirtualMemory</a> for the memory address range. 


## -returns



None




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556374">MmSecureVirtualMemory</a>
 

 

