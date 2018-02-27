---
UID: NF:ntddk.MmFreeNonCachedMemory
title: MmFreeNonCachedMemory function
author: windows-driver-content
description: The MmFreeNonCachedMemory routine releases a range of noncached memory that was allocated by the MmAllocateNonCachedMemory routine.
old-location: kernel\mmfreenoncachedmemory.htm
old-project: kernel
ms.assetid: 284c7e69-50c6-4eef-bcf1-547bc7032a4a
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: MmFreeNonCachedMemory, MmFreeNonCachedMemory routine [Kernel-Mode Driver Architecture], k106_29c317c1-955e-4d0c-9e65-e1aa511c7a8d.xml, kernel.mmfreenoncachedmemory, ntddk/MmFreeNonCachedMemory
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	MmFreeNonCachedMemory
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# MmFreeNonCachedMemory function


## -description


The <b>MmFreeNonCachedMemory</b> routine releases a range of noncached memory that was allocated by the <a href="..\ntddk\nf-ntddk-mmallocatenoncachedmemory.md">MmAllocateNonCachedMemory</a> routine. 


## -syntax


````
VOID MmFreeNonCachedMemory(
  _In_ PVOID  BaseAddress,
  _In_ SIZE_T NumberOfBytes
);
````


## -parameters




### -param BaseAddress [in]

Pointer to the virtual address of the memory to be freed. 


### -param NumberOfBytes [in]

Specifies the size of the range to be freed. This value must match the size passed in a preceding call to <b>MmAllocateNonCachedMemory</b>. 


## -returns



None




## -remarks



The <b>MmFreeNonCachedMemory</b> routine performs the opposite action of <a href="..\ntddk\nf-ntddk-mmallocatenoncachedmemory.md">MmAllocateNonCachedMemory</a>. 




## -see-also

<a href="..\ntddk\nf-ntddk-mmallocatenoncachedmemory.md">MmAllocateNonCachedMemory</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmFreeNonCachedMemory routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

