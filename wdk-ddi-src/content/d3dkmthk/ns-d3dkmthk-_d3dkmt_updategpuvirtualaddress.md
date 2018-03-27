---
UID: NS:d3dkmthk._D3DKMT_UPDATEGPUVIRTUALADDRESS
title: "_D3DKMT_UPDATEGPUVIRTUALADDRESS"
author: windows-driver-content
description: D3DKMT_UPDATEGPUVIRTUALADDRESS is used with UpdateGpuVirtualAddress to allow the driver to specify a number of mapping operations to be applied to the process virtual address space in a single batch of page table updates.
old-location: display\d3dkmt_updategpuvirtualaddress.htm
old-project: display
ms.assetid: B6586406-6CAD-479F-AE41-93EFBA195B99
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_UPDATEGPUVIRTUALADDRESS, D3DKMT_UPDATEGPUVIRTUALADDRESS structure [Display Devices], _D3DKMT_UPDATEGPUVIRTUALADDRESS, d3dkmthk/D3DKMT_UPDATEGPUVIRTUALADDRESS, display.d3dkmt_updategpuvirtualaddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
-	d3dkmthk.h
api_name:
-	D3DKMT_UPDATEGPUVIRTUALADDRESS
product: Windows
targetos: Windows
req.typenames: D3DKMT_UPDATEGPUVIRTUALADDRESS
---

# _D3DKMT_UPDATEGPUVIRTUALADDRESS structure


## -description


<b>D3DKMT_UPDATEGPUVIRTUALADDRESS</b> is used with <a href="https://msdn.microsoft.com/3390A01D-BD4B-4399-AA3E-91BB32264A13">UpdateGpuVirtualAddress</a> to allow the driver to specify a number of mapping operations to be applied to the process virtual address space in a single batch of page table updates. 



## -struct-fields




### -field hDevice

A handle to the device.


### -field hContext

A handle to a context that the map operation will be synchronized against. This also determines which kernel context the map operation will be executed against. In an linked display adapter (LDA) configuration <b>hContext</b> defines a physical GPU whose page tables are modified.


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

Specifies the <b>FenceValue</b> for <b>hFenceObject</b> that the map operation should wait on (unless <b>DoNotWait</b> is 1). When the map operation completes, the fence object will signal <b>hFenceObject</b> with <b>FenceValue</b>+1.


### -field Flags



#### Value

The consolidated value of the <b>Flags</b> union.


### -field Flags.DoNotWait

When set to 1, there will be no wait for the sync objects before executing the operations.


### -field Flags.Reserved

This member is reserved and should be set to zero.

