---
UID: NF:ntddk.MmIsAddressValid
title: MmIsAddressValid function
author: windows-driver-content
description: The MmIsAddressValid routine checks whether a page fault will occur for a read or write operation at a given virtual address.Warning  We do not recommend using this function.
old-location: kernel\mmisaddressvalid.htm
old-project: kernel
ms.assetid: 328f9ffe-67ae-4ba5-98e4-b3b00068eb0e
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: MmIsAddressValid routine [Kernel-Mode Driver Architecture], ntddk/MmIsAddressValid, k106_5f0349a5-5fdb-4263-b91a-d00667729901.xml, MmIsAddressValid, kernel.mmisaddressvalid
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	MmIsAddressValid
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---

# MmIsAddressValid function


## -description


The <b>MmIsAddressValid</b> routine checks whether a page fault will occur for a read or write operation at a given virtual address.
<div class="alert"><b>Warning</b>  We do not recommend using this function.</div><div> </div>

## -syntax


````
BOOLEAN MmIsAddressValid(
  _In_ PVOID VirtualAddress
);
````


## -parameters




### -param VirtualAddress [in]

A pointer to the nonpaged virtual address to check. The caller must ensure that this address cannot be paged out or deleted for the duration of this call. Even after the return from the call, you must not page out or delete this address. If you do page out or delete this address, the return value might be unreliable. Paging out or deleting this address might cause the computer to stop responding (that is, <i>crash</i>). 


## -returns



If no page fault would occur from reading or writing at the given virtual address, <b>MmIsAddressValid</b> returns <b>TRUE</b>.




## -remarks



Even if <b>MmIsAddressValid</b> returns <b>TRUE</b>, accessing the address can cause page faults unless the memory has been locked down or the address is a valid nonpaged pool address. 




## -see-also

<a href="..\wdm\nf-wdm-mmprobeandlockpages.md">MmProbeAndLockPages</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmIsAddressValid routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

