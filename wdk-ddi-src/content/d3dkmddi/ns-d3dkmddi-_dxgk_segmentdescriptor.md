---
UID: NS:d3dkmddi._DXGK_SEGMENTDESCRIPTOR
title: "_DXGK_SEGMENTDESCRIPTOR"
author: windows-driver-content
description: The DXGK_SEGMENTDESCRIPTOR structure contains information about a segment that the driver supports.
old-location: display\dxgk_segmentdescriptor.htm
old-project: display
ms.assetid: d9d79c58-6ef6-4917-b499-fd5a70dc8829
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGK_SEGMENTDESCRIPTOR, DXGK_SEGMENTDESCRIPTOR structure [Display Devices], DmStructs_129432bb-660c-4779-9860-dcc97f3a6ee4.xml, _DXGK_SEGMENTDESCRIPTOR, d3dkmddi/DXGK_SEGMENTDESCRIPTOR, display.dxgk_segmentdescriptor
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
-	DXGK_SEGMENTDESCRIPTOR
product: Windows
targetos: Windows
req.typenames: DXGK_SEGMENTDESCRIPTOR
---

# _DXGK_SEGMENTDESCRIPTOR structure


## -description


The DXGK_SEGMENTDESCRIPTOR structure contains information about a segment that the driver supports. 


## -syntax


````
typedef struct _DXGK_SEGMENTDESCRIPTOR {
  PHYSICAL_ADDRESS  BaseAddress;
  PHYSICAL_ADDRESS  CpuTranslatedAddress;
  SIZE_T            Size;
  UINT              NbOfBanks;
  SIZE_T            *pBankRangeTable;
  SIZE_T            CommitLimit;
  DXGK_SEGMENTFLAGS Flags;
} DXGK_SEGMENTDESCRIPTOR;
````


## -struct-fields




### -field BaseAddress

[out] The base address of the segment, as determined by the graphics processing unit (GPU). The physical address of an allocation that the video memory manager paged in the segment is assigned a GPU address that is offset from the base address that <b>BaseAddress </b>specifies.

The video memory manager ignores the base address of AGP-type aperture segments (where the <b>Agp</b> bit-field flag is specified in the <b>Flags</b> member) and instead uses the actual physical address of the segment within the AGP aperture, as determined on the bus where the GPU is located. In this situation, the driver can use addresses that the video memory manager generated for allocation directly without requiring translation.


### -field CpuTranslatedAddress

[out] The base address of the segment, relative to the bus that the GPU is connected on. For example, when the GPU is connected on the PCI bus, <b>CpuTranslatedAddress </b>is the base address of the usable range that is specified by a PCI base-address register (BAR). The driver specifies this address only if it specifies a CPU-accessible segment by setting the <b>CpuVisible</b> bit-field flag in the <b>Flags</b> member. 

This member is ignored for aperture segments, including the AGP-type aperture segment.  The only exception occurs when the  user-mode display driver has not set up an alternate virtual address for a primary allocation (that is, when the driver has not set <b>UseAlternateVA</b> in the <b>Flags</b> member of the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddicb_lockflags.md">D3DDDICB_LOCKFLAGS</a> structure during a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a> function).

Before the video memory manager maps a virtual address to the physical range, the video memory manager translates this physical address based on the CPU view of the bus and informs the driver about the operation so the driver can set up an aperture to access the content of the segment at the given location. 


### -field Size

[out] The size, in bytes, of the segment. This size must be a multiple of the native host page size (for example, 4 KB on the x86 architecture).

For AGP-type aperture segments (where the <b>Agp</b> bit-field flag is specified in the <b>Flags</b> member), the video memory manager allocates as much aperture space as possible, so  this member is ignored.


### -field NbOfBanks

[out] The number of banks in the segment, if banking is used (that is, if the <b>UseBanking</b> bit-field flag is set in the <b>Flags</b> member).


### -field pBankRangeTable

[out] An array of values that indicates the ranges that delimit each bank in the segment. The array specifies the end addresses of the first bank through the <i>n</i>âˆ’1 bank (that is, the end offsets into the segment for each bank). Note the following: 

<ul>
<li>
Banks are contiguous.

</li>
<li>
The first bank starts at offset zero of the segment.

</li>
<li>
The last bank ends at the end of the segment, so the driver is not required to specify the end address of the last bank.

</li>
<li>
The driver specifies this array only if it also sets the <b>UseBanking</b> bit-field flag in the <b>Flags</b> member.

</li>
</ul>

### -field CommitLimit

[out] The maximum number of bytes that can be committed to the segment. For a memory segment, the commit limit is always the same as the size of the segment, which is specified in the <b>Size</b> member. For an aperture segment, the driver can limit the amount of memory that can be committed to the segment on systems with small amounts of physical memory. 


### -field Flags

[out] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_segmentflags.md">DXGK_SEGMENTFLAGS</a> structure that identifies properties, in bit-field flags, for the segment.

Note that for an AGP-type aperture segment, the driver must exclusively set the <b>Agp</b> member of the structure in the union that DXGK_SEGMENTFLAGS contains. Although the AGP-type aperture segment is an aperture and is accessible to the CPU, if any other members are set, the adapter fails to initialize. 


## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfo.md">DXGK_ALLOCATIONINFO</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_segmentflags.md">DXGK_SEGMENTFLAGS</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_querysegmentout.md">DXGK_QUERYSEGMENTOUT</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a>



<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddicb_lockflags.md">D3DDDICB_LOCKFLAGS</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_querysegmentin.md">DXGK_QUERYSEGMENTIN</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_SEGMENTDESCRIPTOR structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

