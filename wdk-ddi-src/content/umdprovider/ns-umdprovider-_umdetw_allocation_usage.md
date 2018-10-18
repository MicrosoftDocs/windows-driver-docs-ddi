---
UID: NS:umdprovider._UMDETW_ALLOCATION_USAGE
title: "_UMDETW_ALLOCATION_USAGE"
author: windows-driver-content
description: Indicates the reason for mapping from a Microsoft Direct3D memory allocation to a Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys) allocation.
old-location: display\umdetw_allocation_usage.htm
tech.root: display
ms.assetid: 40522471-0fbc-4193-8164-60138e3862fe
ms.date: 5/10/2018
ms.keywords: UMDETW_ALLOCATION_USAGE, UMDETW_ALLOCATION_USAGE structure [Display Devices], _UMDETW_ALLOCATION_USAGE, display.umdetw_allocation_usage, umdprovider/UMDETW_ALLOCATION_USAGE
ms.topic: struct
req.header: umdprovider.h
req.include-header: Umdprovider.h
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
-	umdprovider.h
api_name:
-	UMDETW_ALLOCATION_USAGE
product:
- Windows
targetos: Windows
req.typenames: UMDETW_ALLOCATION_USAGE
---

# _UMDETW_ALLOCATION_USAGE structure


## -description


Indicates the reason for mapping from a Microsoft Direct3D  memory allocation to a Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys) allocation.


## -struct-fields




### -field Packed

The allocation is packed into a larger parent allocation.


### -field Renamed

The allocation is a renamed instance of a Direct3D allocation.


### -field Reserved

Reserved for system use. Do not use in your driver.


### -field DriverReserved

The driver can use these bit fields for its own internal purposes.


### -field Value

A 32-bit value that specifies the allocation mapping.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj542437">UMDEtwLogMapAllocation</a>
 

 

