---
UID: NS:wdm._MDL
title: "_MDL"
author: windows-driver-content
description: An MDL structure is a partially opaque structure that represents a memory descriptor list (MDL).
old-location: kernel\mdl.htm
old-project: kernel
ms.assetid: 71524333-dd5d-4f0b-8dd3-034ea926bc93
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PMDLX, MDL, MDL structure [Kernel-Mode Driver Architecture], PMDL, _MDL, kernel.mdl, kstruct_c_2c589a9a-d775-4fa6-8a37-37212798a215.xml, wdm/MDL"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	MDL
product: Windows
targetos: Windows
req.typenames: MDL, PMDL
---

# _MDL structure


## -description


An <b>MDL</b> structure is a partially opaque structure that represents a memory descriptor list (MDL).


## -struct-fields




### -field Next

Pointer to the next MDL in an MDL chain. For more information about MDL chains, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>.


### -field Size

 


### -field MdlFlags

 


### -field Process

 


### -field MappedSystemVa

 


### -field StartVa

 


### -field ByteCount

 


### -field ByteOffset

 




## -remarks



An MDL describes the layout of a virtual memory buffer in physical memory. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548263">IoAllocateMdl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554530">MmGetMdlByteCount</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554533">MmGetMdlByteOffset</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554537">MmGetMdlPfnArray</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554539">MmGetMdlVirtualAddress</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554568">MmInitializeMdl</a>
 

 

