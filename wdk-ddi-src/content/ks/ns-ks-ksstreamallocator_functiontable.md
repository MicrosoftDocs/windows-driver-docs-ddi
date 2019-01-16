---
UID: NS:ks.__unnamed_struct_43
title: KSSTREAMALLOCATOR_FUNCTIONTABLE
description: Clients can request the function table of a given allocator by sending a KSSTREAMALLOCATOR_FUNCTIONTABLE structure in a KSPROPERTY_STREAMALLOCATOR_FUNCTIONTABLE property request.
old-location: stream\ksstreamallocator_functiontable.htm
tech.root: stream
ms.assetid: 0bc02fa8-41ca-4430-9dff-e98e39b4eeef
ms.date: 04/23/2018
ms.keywords: "*PKSSTREAMALLOCATOR_FUNCTIONTABLE, KSSTREAMALLOCATOR_FUNCTIONTABLE, KSSTREAMALLOCATOR_FUNCTIONTABLE structure [Streaming Media Devices], PKSSTREAMALLOCATOR_FUNCTIONTABLE, PKSSTREAMALLOCATOR_FUNCTIONTABLE structure pointer [Streaming Media Devices], ks-struct_08e285b4-cd29-4f31-9242-3e4bdc6ccf01.xml, ks/KSSTREAMALLOCATOR_FUNCTIONTABLE, ks/PKSSTREAMALLOCATOR_FUNCTIONTABLE, stream.ksstreamallocator_functiontable"
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
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
-	ks.h
api_name:
-	KSSTREAMALLOCATOR_FUNCTIONTABLE
product:
- Windows
targetos: Windows
req.typenames: KSSTREAMALLOCATOR_FUNCTIONTABLE, *PKSSTREAMALLOCATOR_FUNCTIONTABLE
---

# KSSTREAMALLOCATOR_FUNCTIONTABLE structure


## -description


Clients can request the function table of a given allocator by sending a KSSTREAMALLOCATOR_FUNCTIONTABLE structure in a KSPROPERTY_STREAMALLOCATOR_FUNCTIONTABLE property request.


## -struct-fields




### -field AllocateFrame

Points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567151">KStrAllocateFrame</a> routine.


### -field FreeFrame

Points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567174">KStrFreeFrame</a> routine.


## -remarks



This property is only supported by allocators supporting the DISPATCH_LEVEL function interface. Allocators supporting this property must be able to allocate and free frames at IRQL &lt;= DISPATCH_LEVEL.

Because the DISPATCH_LEVEL interface is closely associated with the IRP-based interface, acquiring the function table is likely to result in the creation of an internal notification event to allow pending I/O to be completed when frames are returned to the free list. When the handle to the allocator is closed, the function table pointers are invalid and the associated events are automatically disabled.

This property is only accessible from kernel-mode.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565633">KSPROPERTY_STREAMALLOCATOR_FUNCTIONTABLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567151">KStrAllocateFrame</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567174">KStrFreeFrame</a>
 

 

