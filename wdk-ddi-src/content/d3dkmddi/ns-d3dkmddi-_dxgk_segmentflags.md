---
UID: NS:d3dkmddi._DXGK_SEGMENTFLAGS
title: _DXGK_SEGMENTFLAGS
author: windows-driver-content
description: The DXGK_SEGMENTFLAGS structure identifies properties for a segment that the driver provides through a call to its DxgkDdiQueryAdapterInfo function.
old-location: display\dxgk_segmentflags.htm
old-project: display
ms.assetid: 959dfdb2-cadf-427d-958a-33ce2a1610ae
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgk_segmentflags, _DXGK_SEGMENTFLAGS, DXGK_SEGMENTFLAGS, DXGK_SEGMENTFLAGS structure [Display Devices], DmStructs_a7239928-eb4e-42d0-8ced-9e37d28e9464.xml, d3dkmddi/DXGK_SEGMENTFLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	d3dkmddi.h
apiname: 
-	DXGK_SEGMENTFLAGS
product: Windows
targetos: Windows
req.typenames: DXGK_SEGMENTFLAGS
---

# _DXGK_SEGMENTFLAGS structure


## -description


The DXGK_SEGMENTFLAGS structure identifies properties for a segment that the driver provides through a call to its <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> function.


## -syntax


````
typedef struct _DXGK_SEGMENTFLAGS {
  union {
    struct {
      UINT Aperture  :1;
      UINT Agp  :1;
      UINT CpuVisible  :1;
      UINT UseBanking  :1;
      UINT CacheCoherent  :1;
      UINT PitchAlignment  :1;
      UINT PopulatedFromSystemMemory  :1;
      UINT PreservedDuringStandby  :1;
      UINT PreservedDuringHibernate  :1;
      UINT PartiallyPreservedDuringHibernate  :1;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
      UINT DirectFlip  :1;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_0)
      UINT Use64KBPages  :1;
      UINT ReservedSysMem  :1;
      UINT SupportsCpuHostAperture  :1;
      UINT SupportsCachedCpuHostAperture  :1;
      UINT ApplicationTarget  :1;
      UINT Reserved  :16;
#else 
      UINT Reserved  :21;
#endif 
#else 
      UINT Reserved  :22;
#endif 
    };
    UINT Value;
  };
} DXGK_SEGMENTFLAGS;
````


## -struct-fields




### -field Aperture

[out] A UINT value that specifies whether the segment is an aperture segment instead of a memory segment. An aperture segment does not have physical pages that can hold content for an allocation. When the video memory manager pages an allocation into a memory segment, the memory manager transfers the content of the allocation from the system memory backing store to the segment location. When the video memory manager pages an allocation into an aperture segment, the memory manager maps the physical pages of the allocation backing store into the segment. 

If the driver specifies this member, it must also implement the map-aperture-segment and unmap-aperture-segment operation types for its <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_buildpagingbuffer.md">DxgkDdiBuildPagingBuffer</a> function. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Agp

[out] A UINT value that specifies whether the segment is an <a href="https://msdn.microsoft.com/05a2f942-4374-421e-8292-d122f9fe3571">AGP</a>-type aperture segment, which uses a portion of the AGP aperture that the chipset exposes. The video memory manager allocates the page for the underlying aperture and communicates with the graphic address remapping table (GART) driver to map and unmap memory for the aperture. Because only one AGP segment can exist, the driver should not specify the <b>Agp</b> bit-field flag with any other DXGK_SEGMENTFLAGS bit-field flags. 

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field CpuVisible

[out] A UINT value that specifies whether the memory segment is accessible to the CPU at the address that is specified by the <b>CpuTranslatedAddress</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_segmentdescriptor.md">DXGK_SEGMENTDESCRIPTOR</a> structure that describes the memory segment.

 This member has no meaning for an aperture segment, including the AGP-type aperture segment. The only exception occurs when the  user-mode display driver has not set up an alternate virtual address for a primary allocation (that is, when the driver has not set <b>UseAlternateVA</b> in the <b>Flags</b> member of the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddicb_lockflags.md">D3DDDICB_LOCKFLAGS</a> structure during a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a> function).

See Remarks for more info.

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


### -field UseBanking

[out] A UINT value that specifies whether the segment is divided into banks that the driver uses to provide hints to the video memory manager about the placement of allocations within the segment. The driver should also specify valid bank information in the <b>NbOfBanks</b> and <b>pBankRangeTable</b> members of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_segmentdescriptor.md">DXGK_SEGMENTDESCRIPTOR</a> structure that describes the segment.

Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).


### -field CacheCoherent

[out] A UINT value that specifies whether the aperture segment can maintain cache coherency with cacheable pages that are mapped into the aperture. This member can be set only with setting the <b>Aperture</b> member (that is, <b>CacheCoherent</b> has no meaning for a memory segment).

Setting this member is equivalent to setting the fifth bit of the 32-bit <b>Value</b> member (0x00000010).


### -field PitchAlignment

[out] A UINT value that specifies whether an allocation that is mapped into the segment must be pitch aligned. For this type of segment, the video memory manager uses the <b>Size</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfo.md">DXGK_ALLOCATIONINFO</a> structure for the allocation to allocate a backing store for the allocation. However, the video memory manager uses the <b>PitchAlignedSize</b> member of DXGK_ALLOCATIONINFO to allocate resources for the segment. An allocation that is targeted for this type of segment typically has a different size for the backing store and for the segment. When the backing-store size does not match the segment size, the driver must determine how to correctly move the data in the allocation. This type of segment cannot be used for eviction. 

Setting this member is equivalent to setting the sixth bit of the 32-bit <b>Value</b> member (0x00000020).


### -field PopulatedFromSystemMemory

[out] A UINT value that specifies whether the memory segment is actually populated from system memory that the driver allocated during initialization. If the memory segment is populated from system memory that the BIOS reserved and is not accessible to the operating system (that is, the operating system does not count this system memory when the operating system reports total amount of system memory), the driver should not set this flag. This flag is invalid and ignored on aperture segments.

Setting this member is equivalent to setting the seventh bit of the 32-bit <b>Value</b> member (0x00000040).


### -field PreservedDuringStandby

[out] A UINT value that specifies whether the segment is preserved in a transition to a standby system power state.

For more information on power transition options, see Remarks.

Setting this member is equivalent to setting the eighth bit of the 32-bit <b>Value</b> member (0x00000080).

Supported starting with Windows 8.


### -field PreservedDuringHibernate

[out] A UINT value that specifies whether the segment is preserved in a transition to a hibernate system power state.
<div class="alert"><b>Note</b>  Do not set this flag unless the <b>PreservedDuringStandby</b> member is also set.</div><div> </div>For more information on power transition options, see Remarks.

Setting this member is equivalent to setting the ninth bit of the 32-bit <b>Value</b> member (0x00000100).

Supported starting with Windows 8.


### -field PartiallyPreservedDuringHibernate

[out] A UINT value that specifies whether the segment is  partially preserved in a transition to a hibernate system power state. 
<div class="alert"><b>Note</b>  Do not set this flag unless the <b>PreservedDuringStandby</b> member is also set.</div><div> </div>For more information on power transition options, see Remarks.

Setting this member is equivalent to setting the tenth bit of the 32-bit <b>Value</b> member (0x00000200).

Supported starting with Windows 8.


### -field DirectFlip

[out] A UINT value that specifies whether a segment supports Direct Flip allocations. In this case, the driver must ensure that Direct Flip allocations can be pinned and scanned out from this segment.

Setting this member is equivalent to setting the eleventh bit of the 32-bit <b>Value</b> member (0x00000400).

Supported starting with Windows 8.


### -field Use64KBPages

[out] When set, the GPU memory segment supports 64 KB pages. Otherwise, 4 KB pages are supported. When the driver sets the cap and an allocation can be paged-in to the segment, the allocation alignment, returned by the kernel mode driver from <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfo.md">DXGK_ALLOCATIONINFO</a>, must be multiple a of 64 KB.

Supported starting with Windows 10.


### -field ReservedSysMem

[out] Reserved for system use and should not be set by the kernel mode driver.

Supported starting with Windows 10.


### -field SupportsCpuHostAperture

[out] When set, the segment can be mapped through the CPU host aperture. This flag cannot be used in combination with the <b>CpuVisible</b> flag.

Supported starting with Windows 10.


### -field SupportsCachedCpuHostAperture

[out] When set, this indicates that the hardware supports CPU cache coherent CPU host aperture. Additionally, the <b>SupportsCpuHostAperture</b> flag must be set. The flag is typically set by the software GPU emulation drivers.

Supported starting with Windows 10.


### -field ApplicationTarget

[out] When set, it indicates that this segment should be targeted by application budgets.

Supported starting with Windows 10.


### -field VprSupported

 


### -field VprPreservedDuringStandby

 


### -field EncryptedPagingSupported

 


### -field LocalBudgetGroup

 


### -field NonLocalBudgetGroup

 


### -field Reserved

[out] This member is reserved and should be set to zero.

[out] This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 21 bits (0xFFFFF800) of the 32-bit <b>Value</b> member to zeros.

[out] This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 22 bits (0xFFFFFC00) of the 32-bit <b>Value</b> member to zeros.


### -field Value

[out] A member in the union that DXGK_SEGMENTFLAGS contains that can hold a 32-bit value that identifies properties of the segment.


## -remarks


The driver can specify properties of the segment by setting bits in the 32-bit <b>Value</b> member or by setting individual members of the structure in the union that DXGK_SEGMENTFLAGS contains.

Note that for an AGP-type aperture segment, the driver must exclusively set the <b>Agp</b> member of the structure in the union that DXGK_SEGMENTFLAGS contains. Although the AGP-type aperture segment is an aperture and visible to the CPU, if any other members are set, the adapter fails to initialize.

In the special case where the allocation uses an aperture segment on a shared primary allocation (<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_getstandardallocationdriverdata.md">DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA</a>.<b>StandardAllocationType</b> is <b>D3DKMDT_STANDARDALLOCATION_SHAREDPRIMARYSURFACE</b>), and <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfoflags.md">DXGK_ALLOCATIONINFOFLAGS</a>.<b>UseAlternateVA</b> is not set,  the driver should use a section-backed primary allocation (<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidmmcaps.md">DXGK_VIDMMCAPS</a>.<b>SectionBackedPrimary</b> is set) when the driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> function is called. By using a section-backed primary you can avoid the limitations of <b>CpuVisible</b> for the aperture segment.

You can avoid the limitations of <b>CpuVisible</b> for an aperture segment by using a shared, section-backed primary allocation. In this case, use an aperture segment on a shared primary allocation (<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_getstandardallocationdriverdata.md">DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA</a>.<b>StandardAllocationType</b> is <b>D3DKMDT_STANDARDALLOCATION_SHAREDPRIMARYSURFACE</b>), do not set <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfoflags.md">DXGK_ALLOCATIONINFOFLAGS</a>.<b>UseAlternateVA</b>,  and use a section-backed primary allocation (set <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidmmcaps.md">DXGK_VIDMMCAPS</a>.<b>SectionBackedPrimary</b>) when the driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> function is called. 
<h3><a id="optimized_standby_settings"></a><a id="OPTIMIZED_STANDBY_SETTINGS"></a>Optimized standby settings</h3>The combination of values for the <b>PreservedDuringStandby</b>, <b>PreservedDuringHibernate</b>, and  <b>PartiallyPreservedDuringHibernate</b> members determines whether a segment is purged of its content when the system enters a low-power (standby) system state, as follows.
<table>
<tr>
<th>Preserved During Standby</th>
<th>Preserved During Hibernate</th>
<th>Partially Preserved During Hibernate</th>
<th>Standby State</th>
<th>Hibernate State</th>
</tr>
<tr>
<td>1</td>
<td>1</td>
<td>1</td>
<td>invalid</td>
<td>invalid</td>
</tr>
<tr>
<td>1</td>
<td>1</td>
<td>0</td>
<td>not purged</td>
<td>not purged</td>
</tr>
<tr>
<td>1</td>
<td>0</td>
<td>1</td>
<td>not purged</td>
<td>partially purged</td>
</tr>
<tr>
<td>1</td>
<td>0</td>
<td>0</td>
<td>not purged</td>
<td>purged</td>
</tr>
<tr>
<td>0</td>
<td>1</td>
<td>1</td>
<td>invalid</td>
<td>invalid</td>
</tr>
<tr>
<td>0</td>
<td>1</td>
<td>0</td>
<td>invalid</td>
<td>invalid</td>
</tr>
<tr>
<td>0</td>
<td>0</td>
<td>1</td>
<td>invalid</td>
<td>invalid</td>
</tr>
<tr>
<td>0</td>
<td>0</td>
<td>0</td>
<td>purged</td>
<td>purged</td>
</tr>
</table> 

The operating system does not recognize combinations in this table that are marked "invalid."

If the <a href="https://msdn.microsoft.com/library/windows/hardware/mt608297">hybrid sleep</a> mode is enabled, the system acts as if it is hibernating: it purges segments that are not preserved during hibernate, even if it is going into a low-power state.


The following are common combinations of member values.





## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_segmentdescriptor.md">DXGK_SEGMENTDESCRIPTOR</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfo.md">DXGK_ALLOCATIONINFO</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_buildpagingbuffer.md">DxgkDdiBuildPagingBuffer</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_querysegmentin.md">DXGK_QUERYSEGMENTIN</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_segmentdescriptor3.md">DXGK_SEGMENTDESCRIPTOR3</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_SEGMENTFLAGS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

