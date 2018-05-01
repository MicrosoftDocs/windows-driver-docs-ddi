---
UID: NS:d3dumddi._D3DDDICB_UPDATEGPUVIRTUALADDRESS
title: "_D3DDDICB_UPDATEGPUVIRTUALADDRESS"
author: windows-driver-content
description: D3DDDICB_UPDATEGPUVIRTUALADDRESS is used with pfnUpdateGpuVirtualAddressCb to allow the user mode driver to specify a number of mapping operations to be applied to the process virtual address space in a single batch of page table updates.
old-location: display\d3dddicb_updategpuvirtualaddress.htm
old-project: display
ms.assetid: 6D460EBF-1D5D-4A99-90EE-FCBBC56B8EA4
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DDDICB_UPDATEGPUVIRTUALADDRESS, D3DDDICB_UPDATEGPUVIRTUALADDRESS structure [Display Devices], _D3DDDICB_UPDATEGPUVIRTUALADDRESS, d3dumddi/D3DDDICB_UPDATEGPUVIRTUALADDRESS, display.d3dddicb_updategpuvirtualaddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
api_name:
-	D3DDDICB_UPDATEGPUVIRTUALADDRESS
product: Windows
targetos: Windows
req.typenames: D3DDDICB_UPDATEGPUVIRTUALADDRESS
---

# _D3DDDICB_UPDATEGPUVIRTUALADDRESS structure


## -description


<b>D3DDDICB_UPDATEGPUVIRTUALADDRESS</b> is used with <a href="https://msdn.microsoft.com/99D075A0-4483-47D1-BA24-80C45BFF407A">pfnUpdateGpuVirtualAddressCb</a> to allow the user mode driver to specify a number of mapping operations to be applied to the process virtual address space in a single batch of page table updates. 



## -struct-fields




### -field hContext

Specifies the context against which the map operation will be synchronized against. This also determines which kernel context the map operation will be executed against. In an linked display adapter configuration <b>hContext</b> defines a physical GPU, whose page tables are modified.


### -field hFenceObject

Specifies the monitored fence object to use for synchronization. This should typically be set to the monitored fence used by the user mode driver to track progress of <b>hContext</b>. 


### -field NumOperations

Specifies the number of operations in the <b>Operations</b> array. 


### -field Operations


<a href="https://msdn.microsoft.com/library/windows/hardware/dn906329">D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION</a> array of operations to perform on the GPU virtual address space.


### -field Reserved0

This member is reserved and should be set to zero.


### -field Reserved1

This member is reserved and should be set to zero.


### -field FenceValue

Specifies the <b>FenceValue</b> for <b>hFenceObject</b> that the <i>Map</i> operation should wait on (unless <b>DoNotWait</b> is 1). When the <i>Map</i> operation completes, the fence object will signal <b>hFenceObject</b> with <b>FenceValue</b>+1.


### -field Flags


### -field Flags.DoNotWait

When set to 1, there will be no wait for the sync objects before executing the operations.


### -field Flags.Reserved

This member is reserved and should be set to zero.


### -field Flags.Value

The consolidated value of the <b>Flags</b> union.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906329">D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION</a>



<a href="https://msdn.microsoft.com/99D075A0-4483-47D1-BA24-80C45BFF407A">pfnUpdateGpuVirtualAddressCb</a>
 

 

