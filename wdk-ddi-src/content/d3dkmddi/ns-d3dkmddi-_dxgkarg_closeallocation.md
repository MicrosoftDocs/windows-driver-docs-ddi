---
UID: NS:d3dkmddi._DXGKARG_CLOSEALLOCATION
title: "_DXGKARG_CLOSEALLOCATION"
author: windows-driver-content
description: The DXGKARG_CLOSEALLOCATION structure describes allocations that the display miniport driver should close.
old-location: display\dxgkarg_closeallocation.htm
old-project: display
ms.assetid: ccd65750-b4d0-4955-9fd4-9546709c2390
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGKARG_CLOSEALLOCATION, DXGKARG_CLOSEALLOCATION structure [Display Devices], DmStructs_0d76b996-7ce8-4471-894f-585cc9f3f225.xml, _DXGKARG_CLOSEALLOCATION, d3dkmddi/DXGKARG_CLOSEALLOCATION, display.dxgkarg_closeallocation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGKARG_CLOSEALLOCATION
product: Windows
targetos: Windows
req.typenames: DXGKARG_CLOSEALLOCATION
---

# _DXGKARG_CLOSEALLOCATION structure


## -description


The DXGKARG_CLOSEALLOCATION structure describes allocations that the display miniport driver should close.


## -syntax


````
typedef struct _DXGKARG_CLOSEALLOCATION {
  UINT         NumAllocations;
  const HANDLE *pOpenHandleList;
} DXGKARG_CLOSEALLOCATION;
````


## -struct-fields




### -field NumAllocations

[in] The number of elements in the array that <b>pOpenHandleList</b> specifies.


### -field pOpenHandleList

[in] An array of handles to device-specific allocations to close.


## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_closeallocation.md">DxgkDdiCloseAllocation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_CLOSEALLOCATION structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

