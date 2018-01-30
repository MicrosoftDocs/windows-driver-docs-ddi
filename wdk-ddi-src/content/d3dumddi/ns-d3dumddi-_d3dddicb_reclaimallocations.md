---
UID: NS:d3dumddi._D3DDDICB_RECLAIMALLOCATIONS
title: "_D3DDDICB_RECLAIMALLOCATIONS"
author: windows-driver-content
description: Describes video memory resources that are to be reclaimed and that the user-mode display driver previously offered for reuse. Used with the pfnReclaimAllocationsCb function.
old-location: display\d3dddicb_reclaimallocations.htm
old-project: display
ms.assetid: 61c8fdbf-b003-4caa-af13-ba6f1e22400c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDICB_RECLAIMALLOCATIONS, D3DDDICB_RECLAIMALLOCATIONS structure [Display Devices], d3dumddi/D3DDDICB_RECLAIMALLOCATIONS, _D3DDDICB_RECLAIMALLOCATIONS, display.d3dddicb_reclaimallocations
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3dumddi.h
apiname:
-	D3DDDICB_RECLAIMALLOCATIONS
product: Windows
targetos: Windows
req.typenames: D3DDDICB_RECLAIMALLOCATIONS
---

# _D3DDDICB_RECLAIMALLOCATIONS structure


## -description


Describes video memory resources that are to be reclaimed and that the user-mode display driver  previously offered  for reuse. Used with the  <a href="https://msdn.microsoft.com/library/windows/hardware/hh451695">pfnReclaimAllocationsCb</a> function.


## -syntax


````
typedef struct _D3DDDICB_RECLAIMALLOCATIONS {
  const HANDLE        *pResources;
  const D3DKMT_HANDLE *HandleList;
  BOOL                *pDiscarded;
  UINT                NumAllocations;
} D3DDDICB_RECLAIMALLOCATIONS;
````


## -struct-fields




### -field pResources

[in] A pointer to an array of handles to the resources that are to be reclaimed.

If <b>pResources</b> is not <b>NULL</b>, the <b>HandleList</b> member must be <b>NULL</b>.
<div class="alert"><b>Note</b>  If resources were created with the <b>D3D10_DDI_BIND_PRESENT</b> flag value set in <i>pCreateResource</i>-&gt;<b>BindFlags</b>, the driver must not use the <b>pResources</b> member to reclaim by resource handles. Instead, the driver must reclaim the resources by using allocation handles specified by <b>HandleList</b>.</div><div> </div>

### -field HandleList

[in] An array of D3DKMT_HANDLE data types that represent kernel-mode handles to the allocations that are to be reclaimed.

If <b>HandleList</b> is not <b>NULL</b>, the <b>pResources</b> member must be <b>NULL</b>.


### -field pDiscarded

[out] An  array of Boolean values that specify whether each resource or allocation was discarded.

Each Boolean value in this array corresponds to a resource at the same index location in the arrays pointed to by <b>pResources</b> or   <b>HandleList.</b>

The DirectX graphics kernel subsystem sets each Boolean value to <b>TRUE</b> if the correponding resource was discarded, or to <b>FALSE</b> if not.

The value of <b>pDiscarded</b> can be <b>NULL</b>. If the driver sets it to <b>NULL</b>, the content of the resource or allocation can be assumed to be lost. If the driver does not need the content of the resource or allocation, setting <b>pDiscarded</b> to <b>NULL</b> might improve performance.


### -field NumAllocations

[in] The number of items in the <b>pResources</b>, <b>HandleList</b>, or  <b>pDiscarded</b> members, whichever is not <b>NULL</b>.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451695">pfnReclaimAllocationsCb</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createresource.md">D3D10DDIARG_CREATERESOURCE</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createresource.md">CreateResource(D3D11)</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_RECLAIMALLOCATIONS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

