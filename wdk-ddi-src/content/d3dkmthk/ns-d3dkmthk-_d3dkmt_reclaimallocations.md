---
UID: NS:d3dkmthk._D3DKMT_RECLAIMALLOCATIONS
title: "_D3DKMT_RECLAIMALLOCATIONS"
author: windows-driver-content
description: Describes video memory resources that are to be reclaimed and that the driver previously offered for reuse. Used with the D3DKMTReclaimAllocations function.
old-location: display\d3dkmt_reclaimallocations.htm
old-project: display
ms.assetid: 7fc9295b-90b4-4fa7-abcb-3e3e6a165203
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMT_RECLAIMALLOCATIONS, D3DKMT_RECLAIMALLOCATIONS structure [Display Devices], _D3DKMT_RECLAIMALLOCATIONS, d3dkmthk/D3DKMT_RECLAIMALLOCATIONS, display.d3dkmt_reclaimallocations
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3dkmthk.h
api_name:
-	D3DKMT_RECLAIMALLOCATIONS
product: Windows
targetos: Windows
req.typenames: D3DKMT_RECLAIMALLOCATIONS
---

# _D3DKMT_RECLAIMALLOCATIONS structure


## -description


Describes video memory resources that are to be reclaimed and that the driver  previously offered  for reuse. Used with the  <a href="..\d3dkmthk\nc-d3dkmthk-pfnd3dkmt_reclaimallocations.md">D3DKMTReclaimAllocations</a> function.


## -syntax


````
typedef struct _D3DKMT_RECLAIMALLOCATIONS {
  D3DKMT_HANDLE       hDevice;
  D3DKMT_HANDLE       *pResources;
  const D3DKMT_HANDLE *HandleList;
  BOOL                *pDiscarded;
  UINT                NumAllocations;
} D3DKMT_RECLAIMALLOCATIONS;
````


## -struct-fields




### -field hDevice

[in] A D3DKMT_HANDLE data type that represents a handle to the device that created the allocations.


### -field pResources

[in] An array of <b>D3DKMT_HANDLE</b> data types that represent Direct3D runtime resource handles.


### -field HandleList

[in] An array of <b>D3DKMT_HANDLE</b> data types that represent kernel-mode handles to the allocations that are to be reclaimed.

If <b>HandleList</b> is not <b>NULL</b>, the <b>pResources</b> member must be <b>NULL</b>.


### -field pDiscarded

[out] An  array of Boolean values that specify whether each resource or allocation was discarded.

Each Boolean value in this array corresponds to a resource at the same index location in the arrays pointed to by <b>pResources</b> or   <b>HandleList.</b>

The DirectX graphics kernel subsystem sets each Boolean value to <b>TRUE</b> if the correponding resource was discarded, or to <b>FALSE</b> if not.

The value of <b>pDiscarded</b> can be <b>NULL</b>. If the driver sets it to <b>NULL</b>, the content of the resource or allocation can be assumed to be lost. If the driver does not need the content of the resource or allocation, setting <b>pDiscarded</b> to <b>NULL</b> might improve performance.


### -field NumAllocations

[in] The number of items in the <b>pResources</b>, <b>HandleList</b>, or  <b>pDiscarded</b> members, whichever is not <b>NULL</b>.


## -see-also

<a href="..\d3dkmthk\nc-d3dkmthk-pfnd3dkmt_reclaimallocations.md">D3DKMTReclaimAllocations</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_RECLAIMALLOCATIONS structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

