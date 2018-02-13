---
UID: NS:d3dumddi._D3DDDICB_SETPRIORITY
title: "_D3DDDICB_SETPRIORITY"
author: windows-driver-content
description: The D3DDDICB_SETPRIORITY structure describes the priority level to which to set a resource or list of allocations.
old-location: display\d3dddicb_setpriority.htm
old-project: display
ms.assetid: 8d828d7b-2f86-4fe9-864c-9d0ac4b0ed65
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_D3DDDICB_SETPRIORITY, display.d3dddicb_setpriority, d3dumddi/D3DDDICB_SETPRIORITY, D3DDDICB_SETPRIORITY structure [Display Devices], D3D_param_Structs_38d8110c-0d63-4409-9576-ef9892dae2b7.xml, D3DDDICB_SETPRIORITY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
apiname:
-	D3DDDICB_SETPRIORITY
product: Windows
targetos: Windows
req.typenames: D3DDDICB_SETPRIORITY
---

# _D3DDDICB_SETPRIORITY structure


## -description


The D3DDDICB_SETPRIORITY structure describes the priority level to which to set a resource or list of allocations. 


## -syntax


````
typedef struct _D3DDDICB_SETPRIORITY {
  HANDLE              hResource;
  UINT                NumAllocations;
  const D3DKMT_HANDLE *HandleList;
  const UINT          *pPriorities;
} D3DDDICB_SETPRIORITY;
````


## -struct-fields




### -field hResource

[in] A handle to a resource whose priority must be set. If the user-mode display driver uses the array that is specified by <b>HandleList</b> to set the priority for the list of allocations, it sets <b>hResource</b> to <b>NULL</b>. If the user-mode display driver sets <b>hResource</b> to a non-<b>NULL</b> value, it must set the <b>NumAllocations</b> member to zero and <b>HandleList</b> to <b>NULL</b>. 

If <b>hResource</b> is non-<b>NULL</b>, all of the allocations that belong to the resource are set to the priority that is specified by the first element in the array that <b>pPriorities</b> points to. 


### -field NumAllocations

[in] The number of allocations in the <b>HandleList</b> array. If the user-mode display driver sets the handle in the <b>hResource</b> member to a non-<b>NULL</b> value, it must set <b>NumAllocations</b> to zero.


### -field HandleList

[in] An array of D3DKMT_HANDLE data types that represent kernel-mode handles to the allocations. The Microsoft Direct3D runtime's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_allocatecb.md">pfnAllocateCb</a> function returns these handles. Therefore, the user-mode display driver uses these handles to set priority for the allocations.

If the user-mode display driver sets the handle in the <b>hResource</b> member to a non-<b>NULL</b> value, it must set <b>HandleList</b> to <b>NULL</b>. 


### -field pPriorities

[in] A pointer to an array of priority levels. If the <b>hResource</b> member is non-<b>NULL</b>, the array must contain a single element. If <b>hResource</b> is <b>NULL</b>, the number of elements in the array is specified by the <b>NumAllocations</b> member, and each allocation in the array that is specified by <b>HandleList</b> is set to the priority level of the corresponding element in <b>pPriorities</b>. For a list of defined priority levels, see the Remarks section of the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setprioritycb.md">pfnSetPriorityCb</a> reference page.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setprioritycb.md">pfnSetPriorityCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_allocatecb.md">pfnAllocateCb</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_SETPRIORITY structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

