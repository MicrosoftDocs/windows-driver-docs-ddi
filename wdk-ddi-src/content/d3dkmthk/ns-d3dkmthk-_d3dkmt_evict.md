---
UID: NS:d3dkmthk._D3DKMT_EVICT
title: "_D3DKMT_EVICT"
author: windows-driver-content
description: D3DKMT_EVICT is used with D3DKMTEvict to subtract one from the residency reference count.
old-location: display\d3dkmt_evict.htm
old-project: display
ms.assetid: 07785939-C3D1-4085-BA1A-91E8FEE52B70
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 3, C, D, D3DKMT_EVICT, D3DKMT_EVICT structure [Display Devices], E, I, K, M, T, V, _, _D3DKMT_EVICT, d3dkmthk/D3DKMT_EVICT, display.d3dkmt_evict"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_EVICT
product: Windows
targetos: Windows
req.typenames: D3DKMT_EVICT
---

# _D3DKMT_EVICT structure


## -description


<b>D3DKMT_EVICT</b> is used with <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtevict.md">D3DKMTEvict</a> to subtract one from the residency reference count.

Once this count reaches zero, it will remove the allocation from the device residency list.
  


## -syntax


````
typedef struct _D3DKMT_EVICT {
  D3DKMT_HANDLE       hDevice;
  UINT                NumAllocations;
  const D3DKMT_HANDLE *AllocationList;
  D3DDDI_EVICT_FLAGS  Flags;
  UINT64              NumBytesToTrim;
} D3DKMT_EVICT;
````


## -struct-fields




### -field hDevice

[in] Device that created the allocations passed to this call.


### -field NumAllocations

[in] Number of allocation handles in the <b>AllocationList</b> array.


### -field AllocationList

[in] An array of <b>NumAllocations</b> allocation handles to mark for eviction. All allocations must be created on <b>hDevice</b>.


### -field Flags

[in] Specifies eviction behavior as documented in <a href="..\d3dukmdt\ns-d3dukmdt-d3dddi_evict_flags.md">D3DDDI_EVICT_FLAGS</a>. 


### -field NumBytesToTrim

[out] When non-zero, specifies how much the application should evict in order to meet its current memory budget.


## -see-also

<a href="..\d3dukmdt\ns-d3dukmdt-d3dddi_evict_flags.md">D3DDDI_EVICT_FLAGS</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtevict.md">D3DKMTEvict</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_EVICT structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

