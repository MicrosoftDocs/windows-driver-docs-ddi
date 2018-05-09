---
UID: NS:d3dukmdt.D3DDDI_MAKERESIDENT_FLAGS
title: D3DDDI_MAKERESIDENT_FLAGS
author: windows-driver-content
description: D3DDDI_MAKERESIDENT_FLAGS is used with MakeResident (pfnMakeResidentCb or D3DKMTMakeResident) to instruct the OS to add a resource to the device residency list and increment the residency reference count on this allocation.
old-location: display\d3dddi_makeresident_flags.htm
old-project: display
ms.assetid: 1EC4F8EE-1284-4752-8941-F1C31415BF29
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DDDI_MAKERESIDENT_FLAGS, D3DDDI_MAKERESIDENT_FLAGS structure [Display Devices], d3dukmdt/D3DDDI_MAKERESIDENT_FLAGS, display.d3dddi_makeresident_flags
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
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
-	d3dukmdt.h
api_name:
-	D3DDDI_MAKERESIDENT_FLAGS
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_MAKERESIDENT_FLAGS
---

# D3DDDI_MAKERESIDENT_FLAGS structure


## -description


<b>D3DDDI_MAKERESIDENT_FLAGS</b> is used with <b>MakeResident</b> (<a href="https://msdn.microsoft.com/8D65C3F7-3D07-4341-A989-A1438F821802">pfnMakeResidentCb</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/dn906775">D3DKMTMakeResident</a>) to instruct the OS to add a resource to the device residency list and increment the residency reference count on this allocation.


## -struct-fields




### -field CantTrimFurther

This flag should be used after the user mode driver has trimmed all other possible resources in the device and require the current resource to be made resident in order to make forward progress on a particular single atomic operation.


### -field MustSucceed

This flag may only be set if <b>CantTrimFurther</b> is also set. It indicates that the resource being made resident is critical to the device forward progress. If the video memory manager can’t satisfy the request the device will be put in error.


### -field Reserved

This member is reserved and should be set to zero.


### -field Value

The consolidated value of the structure.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906775">D3DKMTMakeResident</a>



<a href="https://msdn.microsoft.com/8D65C3F7-3D07-4341-A989-A1438F821802">pfnMakeResidentCb</a>
 

 

