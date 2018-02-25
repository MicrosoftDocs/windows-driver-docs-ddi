---
UID: NE:wdfmemory._WDF_MEMORY_DESCRIPTOR_TYPE
title: "_WDF_MEMORY_DESCRIPTOR_TYPE"
author: windows-driver-content
description: The WDF_MEMORY_DESCRIPTOR_TYPE enumeration identifies the types of memory descriptions that a WDF_MEMORY_DESCRIPTOR structure can specify.
old-location: wdf\wdf_memory_descriptor_type.htm
old-project: wdf
ms.assetid: ab364ad8-1b04-4ad0-a036-9b1c41e16604
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , ,, C, D, DFMemoryObjectRef_3817f18e-3d20-43d6-b6f0-584c1533fe9a.xml, E, F, I, M, O, P, R, S, T, W, WDF_MEMORY_DESCRIPTOR_TYPE, WDF_MEMORY_DESCRIPTOR_TYPE enumeration, WdfMemoryDescriptorTypeBuffer, WdfMemoryDescriptorTypeHandle, WdfMemoryDescriptorTypeInvalid, WdfMemoryDescriptorTypeMdl, Y, _, _WDF_MEMORY_DESCRIPTOR_TYPE, kmdf.wdf_memory_descriptor_type, wdf.wdf_memory_descriptor_type, wdfmemory/WDF_MEMORY_DESCRIPTOR_TYPE, wdfmemory/WdfMemoryDescriptorTypeBuffer, wdfmemory/WdfMemoryDescriptorTypeHandle, wdfmemory/WdfMemoryDescriptorTypeInvalid, wdfmemory/WdfMemoryDescriptorTypeMdl"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfmemory.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfmemory.h
apiname:
-	WDF_MEMORY_DESCRIPTOR_TYPE
product: Windows
targetos: Windows
req.typenames: WDF_MEMORY_DESCRIPTOR_TYPE
req.product: Windows 10 or later.
---

# _WDF_MEMORY_DESCRIPTOR_TYPE enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_MEMORY_DESCRIPTOR_TYPE</b> enumeration identifies the types of memory descriptions that a <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure can specify.


## -syntax


````
typedef enum _WDF_MEMORY_DESCRIPTOR_TYPE { 
  WdfMemoryDescriptorTypeInvalid  = 0,
  WdfMemoryDescriptorTypeBuffer   = 1,
  WdfMemoryDescriptorTypeMdl      = 2,
  WdfMemoryDescriptorTypeHandle   = 3
} WDF_MEMORY_DESCRIPTOR_TYPE;
````


## -enum-fields




### -field WdfMemoryDescriptorTypeInvalid

Reserved for internal use only.


### -field WdfMemoryDescriptorTypeBuffer

The <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure contains a buffer description.


### -field WdfMemoryDescriptorTypeMdl

The <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure contains a memory descriptor list (MDL).


### -field WdfMemoryDescriptorTypeHandle

The <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure contains a handle to a memory object.


## -see-also

<a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_MEMORY_DESCRIPTOR_TYPE enumeration%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

