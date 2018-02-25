---
UID: NE:ntifs._MEMORY_INFORMATION_CLASS
title: "_MEMORY_INFORMATION_CLASS"
author: windows-driver-content
description: Defines classes of memory information that can be retrieved by using the ZwQueryVirtualMemory function.
old-location: kernel\memory_information_class.htm
old-project: kernel
ms.assetid: 7E3B531F-935C-41D6-94F7-DB18F82B9109
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , ,, A, C, E, F, I, L, M, MEMORY_INFORMATION_CLASS, MEMORY_INFORMATION_CLASS enumeration [Kernel-Mode Driver Architecture], MemoryBasicInformation, N, O, R, S, T, Y, _, _MEMORY_INFORMATION_CLASS, kernel.memory_information_class, ntifs/MEMORY_INFORMATION_CLASS, ntifs/MemoryBasicInformation"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntifs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10.
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	MEMORY_INFORMATION_CLASS
product: Windows
targetos: Windows
req.typenames: MEMORY_INFORMATION_CLASS
---

# _MEMORY_INFORMATION_CLASS enumeration


## -description


Defines classes of memory information that can be retrieved by using the  <a href="..\ntifs\nf-ntifs-zwqueryvirtualmemory.md">ZwQueryVirtualMemory</a> function.


## -syntax


````
typedef enum _MEMORY_INFORMATION_CLASS { 
  MemoryBasicInformation
} MEMORY_INFORMATION_CLASS;
````


## -enum-fields




### -field MemoryBasicInformation

Memory information described in the <a href="..\ntifs\ns-ntifs-_memory_basic_information.md">MEMORY_BASIC_INFORMATION</a> structure will be retrieved.


## -remarks



Currently, only the <b>MemoryBasicInformation</b> value is supported for use with the <a href="..\ntifs\nf-ntifs-zwqueryvirtualmemory.md">ZwQueryVirtualMemory</a> routine.




## -see-also

<a href="..\ntifs\nf-ntifs-zwqueryvirtualmemory.md">ZwQueryVirtualMemory</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MEMORY_INFORMATION_CLASS enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

