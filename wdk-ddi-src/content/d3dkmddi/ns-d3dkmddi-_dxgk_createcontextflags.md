---
UID: NS:d3dkmddi._DXGK_CREATECONTEXTFLAGS
title: "_DXGK_CREATECONTEXTFLAGS"
author: windows-driver-content
description: The DXGK_CREATECONTEXTFLAGS structure identifies how to create contexts.
old-location: display\dxgk_createcontextflags.htm
old-project: display
ms.assetid: f7cadf78-c908-4034-889d-b5c7d0ffdaad
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGK_CREATECONTEXTFLAGS, DXGK_CREATECONTEXTFLAGS structure [Display Devices], DmStructs_19418464-77f9-407f-8b04-c6a35561069b.xml, _DXGK_CREATECONTEXTFLAGS, d3dkmddi/DXGK_CREATECONTEXTFLAGS, display.dxgk_createcontextflags
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
-	DXGK_CREATECONTEXTFLAGS
product: Windows
targetos: Windows
req.typenames: DXGK_CREATECONTEXTFLAGS
---

# _DXGK_CREATECONTEXTFLAGS structure


## -description


The DXGK_CREATECONTEXTFLAGS structure identifies how to create contexts.


## -struct-fields




### -field SystemContext

A UINT value that specifies whether contexts that a driver's <a href="https://msdn.microsoft.com/aea21a36-f3d5-4541-bd2d-aa026668c562">DxgkDdiCreateContext</a> function creates are system contexts for the engine that the <b>EngineAffinity</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557567">DXGKARG_CREATECONTEXT</a> structure specifies. A system context is created for the paging engine only.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field GdiContext

A UINT value that specifies whether the contexts that a driver's <a href="https://msdn.microsoft.com/aea21a36-f3d5-4541-bd2d-aa026668c562">DxgkDdiCreateContext</a> function creates are GDI-specific contexts for the engine that the <b>EngineAffinity</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557567">DXGKARG_CREATECONTEXT</a> structure specifies.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).

This member is available beginning with Windows 7.


### -field VirtualAddressing

A UINT value that specifies whether the contexts that a driver's <a href="https://msdn.microsoft.com/aea21a36-f3d5-4541-bd2d-aa026668c562">DxgkDdiCreateContext</a> function creates use virtual addressing.

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).

Supported starting with Windows 10.


### -field SystemProtectedContext

A UINT value that specifies whether the context being used to modify the VPR will have access to allocations outside the VPR.

Supported starting with Windows 10.


### -field HwQueueSupported

 


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 28 bits (0xFFFFFFFB) of the 32-bit <b>Value</b> member to zeros.


#### - Value

A member in the union that DXGK_CREATECONTEXTFLAGS contains that can hold a 32-bit value that identifies how to create contexts.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557567">DXGKARG_CREATECONTEXT</a>



<a href="https://msdn.microsoft.com/aea21a36-f3d5-4541-bd2d-aa026668c562">DxgkDdiCreateContext</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_CREATECONTEXTFLAGS structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

