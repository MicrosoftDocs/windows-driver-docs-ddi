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

Starting with Windows 8, the operating system calls this function during a bugcheck operation following a system stop error. The operating system calls this function only if the display device was previously reset through a call to <a href="..\dispmprt\nc-dispmprt-dxgkddi_system_display_enable.md">DxgkDdiSystemDisplayEnable</a>.


## -prototype


````
DXGKDDI_SYSTEM_DISPLAY_WRITE DxgkDdiSystemDisplayWrite;

VOID* DxgkDdiSystemDisplayWrite(
  _In_ PVOID MiniportDeviceContext,
  _In_ PVOID Source,
  _In_ UINT  SourceWidth,
  _In_ UINT  SourceHeight,
  _In_ UINT  SourceStride,
  _In_ UINT  PositionX,
  _In_ UINT  PositionY
)
{ ... }
````


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem.




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
The color format of the source image is always in the <b>D3DDDIFMT_R8G8B8</b> (24 bits per pixel) or <b>D3DDDIFMT_A8R8G8B8</b> (32 bpp) formats of the <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a> enumeration. The display miniport driver had previously set the display mode to enable write operations in this format when its <a href="..\dispmprt\nc-dispmprt-dxgkddi_system_display_enable.md">DxgkDdiSystemDisplayEnable</a> was called.

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

<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_stop_device_and_release_post_display_ownership.md">DxgkDdiStopDeviceAndReleasePostDisplayOwnership</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_system_display_enable.md">DxgkDdiSystemDisplayEnable</a>



<a href="https://msdn.microsoft.com/6454adb3-c958-467b-acbc-b8937b98cd57">DxgkCbAcquirePostDisplayOwnership</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_SYSTEM_DISPLAY_WRITE callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

