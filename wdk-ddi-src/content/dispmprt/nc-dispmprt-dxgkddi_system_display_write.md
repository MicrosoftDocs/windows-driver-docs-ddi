---
UID: NC:dispmprt.DXGKDDI_SYSTEM_DISPLAY_WRITE
title: DXGKDDI_SYSTEM_DISPLAY_WRITE
author: windows-driver-content
description: Called by the operating system to request the display miniport driver to write an image block to the display device.
old-location: display\dxgkddisystemdisplaywrite.htm
old-project: display
ms.assetid: 5C0F9878-522C-4DDE-A790-54C94880F119
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_SYSTEM_DISPLAY_WRITE, DxgkDdiSystemDisplayWrite, DxgkDdiSystemDisplayWrite callback function [Display Devices], display.dxgkddisystemdisplaywrite, dispmprt/DxgkDdiSystemDisplayWrite
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: 
req.target-type: Desktop
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
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dispmprt.h
api_name:
-	DxgkDdiSystemDisplayWrite
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKDDI_SYSTEM_DISPLAY_WRITE callback


## -description


Called by the operating system to request the display miniport driver to write an image block to the display device.

Starting with Windows 8, the operating system calls this function during a bugcheck operation following a system stop error. The operating system calls this function only if the display device was previously reset through a call to <a href="https://msdn.microsoft.com/D938F7F4-E1FA-4C63-A31D-5ED160276565">DxgkDdiSystemDisplayEnable</a>.


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem.




### -param Source [in]

A pointer to the start address of the source image to be written to the bugcheck screen that displays information about the system stop error.


### -param SourceWidth [in]

A UINT value that specifies the width, in units of pixels, of the specified source image.


### -param SourceHeight [in]

A UINT value that specifies the height, in units of pixels, of the specified source image.


### -param SourceStride [in]

A UINT value that specifies the number of bytes for each line of the specified source image.


### -param PositionX [in]

A UINT value that specifies the starting X coordinate that the specified source image should be written to on the display device.


### -param PositionY [in]

A UINT value that specifies the starting Y coordinate that the specified source image should be written to on the display device.


## -returns



This callback function does not return a value.




## -remarks



<h3><a id="Source_image_restrictions"></a><a id="source_image_restrictions"></a><a id="SOURCE_IMAGE_RESTRICTIONS"></a>Source image restrictions</h3>
The display miniport driver must follow these guidelines when its <i>DxgkDdiSystemDisplayWrite</i> function is called:

<ul>
<li>
The color format of the source image is always in the <b>D3DDDIFMT_R8G8B8</b> (24 bits per pixel) or <b>D3DDDIFMT_A8R8G8B8</b> (32 bpp) formats of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a> enumeration. The display miniport driver had previously set the display mode to enable write operations in this format when its <a href="https://msdn.microsoft.com/D938F7F4-E1FA-4C63-A31D-5ED160276565">DxgkDdiSystemDisplayEnable</a> was called.

</li>
<li>
The source image is in non-paged memory. The display miniport driver should write this source image to the current frame buffer starting at the positions specified by the <i>PostionX</i> and <i>PositionY</i> parameters.

</li>
<li>
	The display miniport driver should use the CPU to write the image block to the frame buffer. When the system encounters a stop error, it may have been caused by a continuous timeout detection and recovery (TDR) on the display device.  In that case, the graphics processing unit (GPU) might be in an unknown state.

For more information about TDR, see <a href="https://msdn.microsoft.com/f410eec7-026f-41e0-8c60-72f651659ead">Timeout Detection and Recovery (TDR)</a>.

</li>
</ul>
<h3><a id="Use_non-paged_memory"></a><a id="use_non-paged_memory"></a><a id="USE_NON-PAGED_MEMORY"></a>Use non-paged memory</h3>
Windows kernel-mode functions might not be available while this function is being called.

<i>DxgkDdiSystemDisplayWrite</i> can be called at any IRQL, so it must be in nonpageable memory. <i>DxgkDdiSystemDisplayWrite</i> must not call any code that is in pageable memory and must not manipulate any data that is in pageable memory.




## -see-also




<a href="https://msdn.microsoft.com/6454adb3-c958-467b-acbc-b8937b98cd57">DxgkCbAcquirePostDisplayOwnership</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>



<a href="https://msdn.microsoft.com/6AF170BF-C422-4340-8935-31A4D4F3EFA5">DxgkDdiStopDeviceAndReleasePostDisplayOwnership</a>



<a href="https://msdn.microsoft.com/D938F7F4-E1FA-4C63-A31D-5ED160276565">DxgkDdiSystemDisplayEnable</a>
 

 

