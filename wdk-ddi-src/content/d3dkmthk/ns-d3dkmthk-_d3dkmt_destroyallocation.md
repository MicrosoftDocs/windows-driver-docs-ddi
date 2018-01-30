---
UID: NS:d3dkmthk._D3DKMT_DESTROYALLOCATION
title: "_D3DKMT_DESTROYALLOCATION"
author: windows-driver-content
description: The D3DKMT_DESTROYALLOCATION structure describes parameters for releasing allocations.
old-location: display\d3dkmt_destroyallocation.htm
old-project: display
ms.assetid: ba85b333-9a43-421a-8687-9630e792cadf
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: OpenGL_Structs_46425135-17f7-4b12-8e01-1247e3e1ab63.xml, d3dkmthk/D3DKMT_DESTROYALLOCATION, D3DKMT_DESTROYALLOCATION structure [Display Devices], display.d3dkmt_destroyallocation, _D3DKMT_DESTROYALLOCATION, D3DKMT_DESTROYALLOCATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_DESTROYALLOCATION
product: Windows
targetos: Windows
req.typenames: D3DKMT_DESTROYALLOCATION
---

# _D3DKMT_DESTROYALLOCATION structure


## -description


The D3DKMT_DESTROYALLOCATION structure describes parameters for releasing allocations.


## -syntax


````
typedef struct _D3DKMT_DESTROYALLOCATION {
  D3DKMT_HANDLE       hDevice;
  D3DKMT_HANDLE       hResource;
  const D3DKMT_HANDLE *phAllocationList;
  UINT                AllocationCount;
} D3DKMT_DESTROYALLOCATION;
````


## -struct-fields




### -field hDevice

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the device that the resource, allocations, or both are associated with.


### -field hResource

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the resource that is associated with the allocations when releasing a resource. If a resource handle is specified, all of the allocations that are associated with it are automatically released.


### -field phAllocationList

[in] An array of D3DKMT_HANDLE data types that represent kernel-mode handles to the allocations. If any allocation in the list is associated with a resource, all of the allocations in the list must also be associated with the same resource. If the OpenGL ICD sets the handle in the <b>hResource</b> member to a non-<b>NULL</b> value, the ICD must set <b>phAllocationList</b> to <b>NULL</b>.


### -field AllocationCount

[in] The number of allocations in the array that <b>phAllocationList</b> specifies. If the OpenGL ICD sets the handle in the <b>hResource</b> member to a non-<b>NULL</b> value, the <b>AllocationCount</b> member is ignored by the OpenGL runtime.


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtdestroyallocation.md">D3DKMTDestroyAllocation</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_DESTROYALLOCATION structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

