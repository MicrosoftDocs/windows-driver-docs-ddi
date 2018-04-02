---
UID: NS:d3dkmddi._DXGK_SETVIDPNSOURCEADDRESS_FLAGS
title: "_DXGK_SETVIDPNSOURCEADDRESS_FLAGS"
author: windows-driver-content
description: The DXGK_SETVIDPNSOURCEADDRESS_FLAGS structure identifies the specific type of operation to perform in a call to the display miniport driver's DxgkDdiSetVidPnSourceAddress or DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay functions.
old-location: display\dxgk_setvidpnsourceaddress_flags.htm
old-project: display
ms.assetid: cdc4aec6-45d4-4a5b-aa52-7830494a12b6
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGK_SETVIDPNSOURCEADDRESS_FLAGS, DXGK_SETVIDPNSOURCEADDRESS_FLAGS structure [Display Devices], DmStructs_45e34e9d-e410-44f4-a41a-aad748f01688.xml, _DXGK_SETVIDPNSOURCEADDRESS_FLAGS, d3dkmddi/DXGK_SETVIDPNSOURCEADDRESS_FLAGS, display.dxgk_setvidpnsourceaddress_flags
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_SETVIDPNSOURCEADDRESS_FLAGS
product: Windows
targetos: Windows
req.typenames: DXGK_SETVIDPNSOURCEADDRESS_FLAGS
---

# _DXGK_SETVIDPNSOURCEADDRESS_FLAGS structure


## -description


The DXGK_SETVIDPNSOURCEADDRESS_FLAGS structure identifies the specific type of operation to perform in a call to the display miniport driver's <a href="https://msdn.microsoft.com/488c929b-3816-457f-b5c2-c176b93d5546">DxgkDdiSetVidPnSourceAddress</a> or <a href="https://msdn.microsoft.com/95108e45-1a3a-4a75-8719-0caadb911469">DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay</a> functions.


## -struct-fields




### -field ModeChange

A UINT value that specifies for the driver to switch the display mode. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field FlipImmediate

A UINT value that specifies for the driver to perform a flip operation that occurs without vertical sync.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field FlipOnNextVSync

A UINT value that specifies for the driver to perform a flip operation that occurs on the next vertical sync.

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


### -field FlipStereo

[in] Supported beginning with Windows 8.

Specifies whether the driver  flips both left and right images of a stereo allocation.

If the <b>FlipOnNextVSync</b> member of the <b>DXGK_SETVIDPNSOURCEADDRESS_FLAGS</b> structure is  set, the driver completes the flip to the left image on the next VSync and then completes the flip to the right image on the following VSync.

If the <b>FlipImmediate</b> member of the <b>DXGK_SETVIDPNSOURCEADDRESS_FLAGS</b> structure is  set, the driver immediately starts to scan out from the new allocation. For example, if the driver was scanning a right image, it  starts the new scan from the same relative offset in the right image of the new allocation.

The <b>FlipStereo</b> and <b>FlipStereoTemporaryMono</b> members cannot both be set at the same time.

For more requirements, see the Remarks section.

Setting this member is equivalent to setting the    fourth bit of the 32-bit <b>Value</b> member (0x00000008).


### -field FlipStereoTemporaryMono

[in] Supported beginning with Windows 8.

Specifies whether the driver uses the left image of a stereo allocation for the right and left portions of a stereo frame. The driver performs the same present operation as with <b>FlipStereo</b>, except that it scans out only from the left image to produce both images of a stereo frame.

This member should  be set only if the driver reports support for this option in the current display mode by setting the <b>Type</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546724">D3DKMDT_VIDPN_SOURCE_MODE</a> structure to D3DKMDT_RMT_GRAPHICS_STEREO_ADVANCED_SCAN.

The <b>FlipStereo</b> and <b>FlipStereoTemporaryMono</b> members cannot both be set at the same time.

The   <b>FlipStereoTemporaryMono</b> and <b>FlipStereoPreferRight</b> members cannot both be set at the same time.

For more requirements, see the Remarks section.

Setting this member is equivalent to setting the    fifth bit of the 32-bit <b>Value</b> member (0x00000010).


### -field FlipStereoPreferRight

[in] Supported beginning with Windows 8.

Specifies that when the driver clones a stereo primary allocation to a mono monitor, it uses the right image.

The   <b>FlipStereoTemporaryMono</b> and <b>FlipStereoPreferRight</b> members cannot both be set at the same time.

For more requirements, see the Remarks section.

Setting this member is equivalent to setting the    sixth bit of the 32-bit <b>Value</b> member (0x00000020).


### -field SharedPrimaryTransition

[in] Supported beginning with Windows 8.

Specifies that the driver is transitioning to or from a shared managed primary allocation.

This member is set if either of the following transitions occurs:

<ul>
<li>The current primary allocation is not a shared primary allocation, but the new one is.</li>
<li>The current primary allocation is a shared primary allocation, but the new one is not.</li>
</ul>
When <b>SharedPrimaryTransition</b> is set, the display miniport driver must validate that the hardware can seamlessly switch back and forth between primary and shared primary allocations, and it must perform any hardware programming needed to make the seamless switch occur.

Setting this member is equivalent to setting the    seventh bit of the 32-bit <b>Value</b> member (0x00000040).


### -field IndependentFlipExclusive

[in] Supported beginning with Windows 10.

When <b>IndependentFlipExlusive</b> is set, the flip is done in the independent flip exclusive mode. The front buffer is accessed only by the display hardware (not by the DWM) and the kernel mode driver can apply vertical sync-related optimizations.   



### -field MoveFlip

[in] Supported beginning with Windows 10.

When <b>MoveFlip</b> is set, the  driver is notified to use any state that has been saved from the previous flip to configure the new scanout request.


### -field Reserved

[in] This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 23 bits (0xFFFFFF00) of the 32-bit <b>Value</b> member to zeros.


#### - Value

A member in the union that DXGK_SETVIDPNSOURCEADDRESS_FLAGS contains that can hold a 32-bit value that identifies operation type. 


## -remarks



If any of the <b>FlipStereo</b>, <b>FlipStereoTemporaryMono</b>, or <b>FlipStereoPreferRight</b>  members are set, these conditions apply:

<ul>
<li>The <b>hAllocation</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559484">DXGKARG_SETVIDPNSOURCEADDRESS</a> structure points to an allocation that is created with the <b>Stereo</b> member set in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547942">D3DKMT_DISPLAYMODE</a> structure.</li>
<li>The <b>PrimarySegment</b> and <b>PrimaryAddress</b> members of <a href="https://msdn.microsoft.com/library/windows/hardware/ff559484">DXGKARG_SETVIDPNSOURCEADDRESS</a> point to the starting physical address of the allocation.</li>
<li>The driver honors the settings of the <b>FlipImmediate</b> and <b>FlipOnNextVSync</b> members of  the <b>DXGK_SETVIDPNSOURCEADDRESS_FLAGS</b> structure.</li>
</ul>
Beginning with Windows 8, the display miniport driver can fail a call to the <a href="https://msdn.microsoft.com/488c929b-3816-457f-b5c2-c176b93d5546">DxgkDdiSetVidPnSourceAddress</a> function, returning STATUS_INVALID_PARAMETER, when the <b>SharedPrimaryTransition</b> member is set in <i>pSetVidPnSourceAddress</i>-&gt;<b>Flags</b>. However, such a failure is not expected unless there is an error in either the user mode driver's implementation of the <a href="https://msdn.microsoft.com/BB909041-0194-4828-ACA2-E3F6B1974DBB">CheckDirectFlipSupport</a> function or in the Desktop Window Manager (DWM). If such a failure occurs, the operating system will not seamlessly fail back to composition mode, and presentation will be incorrect.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547942">D3DKMT_DISPLAYMODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559484">DXGKARG_SETVIDPNSOURCEADDRESS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562052">DXGK_SETVIDPNSOURCEADDRESS_FLAGS</a>



<a href="https://msdn.microsoft.com/488c929b-3816-457f-b5c2-c176b93d5546">DxgkDdiSetVidPnSourceAddress</a>



<a href="https://msdn.microsoft.com/95108e45-1a3a-4a75-8719-0caadb911469">DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay</a>
 

 

