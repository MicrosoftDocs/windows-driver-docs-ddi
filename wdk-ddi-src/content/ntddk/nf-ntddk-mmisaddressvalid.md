---
UID: NF:ntddk.MmIsAddressValid
title: MmIsAddressValid function
author: windows-driver-content
description: The MmIsAddressValid routine checks whether a page fault will occur for a read or write operation at a given virtual address.Warning  We do not recommend using this function.
old-location: kernel\mmisaddressvalid.htm
old-project: kernel
ms.assetid: 328f9ffe-67ae-4ba5-98e4-b3b00068eb0e
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: MmIsAddressValid, MmIsAddressValid routine [Kernel-Mode Driver Architecture], k106_5f0349a5-5fdb-4263-b91a-d00667729901.xml, kernel.mmisaddressvalid, ntddk/MmIsAddressValid
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	MmIsAddressValid
product: Windows
targetos: Windows
req.typenames: 
---

# MmIsAddressValid function


## -description


The <b>MmIsAddressValid</b> routine checks whether a page fault will occur for a read or write operation at a given virtual address.
<div class="alert"><b>Warning</b>  We do not recommend using this function.</div><div> </div>

## -parameters




### -param VirtualAddress [in]

A pointer to the nonpaged virtual address to check. The caller must ensure that this address cannot be paged out or deleted for the duration of this call. Even after the return from the call, you must not page out or delete this address. If you do page out or delete this address, the return value might be unreliable. Paging out or deleting this address might cause the computer to stop responding (that is, <i>crash</i>). 


## -returns



If no page fault would occur from reading or writing at the given virtual address, <b>MmIsAddressValid</b> returns <b>TRUE</b>.




## -remarks



Even if <b>MmIsAddressValid</b> returns <b>TRUE</b>, accessing the address can cause page faults unless the memory has been locked down or the address is a valid nonpaged pool address. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554664">MmProbeAndLockPages</a>
 

 

