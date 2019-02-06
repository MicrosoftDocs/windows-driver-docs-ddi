---
UID: NE:d3dkmddi._DXGK_PAGETABLEUPDATEMODE
title: _DXGK_PAGETABLEUPDATEMODE (d3dkmddi.h)
description: DXGK_PAGETABLEUPDATEMODE is used as part of a DxgkDdiBuildPagingBuffer operation to indicate which member of the related DXGK_PAGETABLEUPDATEADDRESS structure contains the address of the page table to update.
old-location: display\dxgk_pagetableupdatemode.htm
ms.assetid: E7C823B1-457E-4B86-B44B-DC5BD48CF98E
ms.date: 05/10/2018
ms.keywords: DXGK_PAGETABLEUPDATEMODE, DXGK_PAGETABLEUPDATEMODE enumeration [Display Devices], DXGK_PAGETABLEUPDATE_CPU_VIRTUAL, DXGK_PAGETABLEUPDATE_GPU_PHYSICAL, DXGK_PAGETABLEUPDATE_GPU_VIRTUAL, _DXGK_PAGETABLEUPDATEMODE, d3dkmddi/DXGK_PAGETABLEUPDATEMODE, d3dkmddi/DXGK_PAGETABLEUPDATE_CPU_VIRTUAL, d3dkmddi/DXGK_PAGETABLEUPDATE_GPU_PHYSICAL, d3dkmddi/DXGK_PAGETABLEUPDATE_GPU_VIRTUAL, display.dxgk_pagetableupdatemode
ms.topic: enum
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	d3dkmddi.h
api_name:
-	DXGK_PAGETABLEUPDATEMODE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_PAGETABLEUPDATEMODE
---

# _DXGK_PAGETABLEUPDATEMODE enumeration


## -description


<b>DXGK_PAGETABLEUPDATEMODE</b> is used as part of a <a href="https://msdn.microsoft.com/d315ff53-4a9f-46a3-ad74-d65a5eb72de1">DxgkDdiBuildPagingBuffer</a> operation to indicate which member of the related <a href="https://msdn.microsoft.com/library/windows/hardware/dn914480">DXGK_PAGETABLEUPDATEADDRESS</a> structure contains the address of the page table to update. 


## -enum-fields




### -field DXGK_PAGETABLEUPDATE_CPU_VIRTUAL

Indicates that the address of the page table to update is in the <b>CpuVirtual</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn914480">DXGK_PAGETABLEUPDATEADDRESS</a> structure.


### -field DXGK_PAGETABLEUPDATE_GPU_VIRTUAL

Indicates that the address of the page table to update is in the <b>GpuVirtual</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn914480">DXGK_PAGETABLEUPDATEADDRESS</a> structure.


### -field DXGK_PAGETABLEUPDATE_GPU_PHYSICAL

Indicates that the address of the page table to update is in the <b>GpuPhysical</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn914480">DXGK_PAGETABLEUPDATEADDRESS</a> structure.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn914480">DXGK_PAGETABLEUPDATEADDRESS</a>



<a href="https://msdn.microsoft.com/d315ff53-4a9f-46a3-ad74-d65a5eb72de1">DxgkDdiBuildPagingBuffer</a>
 

 

