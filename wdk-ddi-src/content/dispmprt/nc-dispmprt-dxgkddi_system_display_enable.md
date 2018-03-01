---
UID: NC:dispmprt.DXGKDDI_SYSTEM_DISPLAY_ENABLE
title: DXGKDDI_SYSTEM_DISPLAY_ENABLE
author: windows-driver-content
description: Called by the operating system to request the display miniport driver to reset the current display device to a specified state.
old-location: display\dxgkddisystemdisplayenable.htm
old-project: display
ms.assetid: D938F7F4-E1FA-4C63-A31D-5ED160276565
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_SYSTEM_DISPLAY_ENABLE, DxgkDdiSystemDisplayEnable, DxgkDdiSystemDisplayEnable callback function [Display Devices], display.dxgkddisystemdisplayenable, dispmprt/DxgkDdiSystemDisplayEnable
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
-	DxgkDdiSystemDisplayEnable
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKDDI_SYSTEM_DISPLAY_ENABLE callback


## -description


Called by the operating system to request the display miniport driver to reset the current  display device to a specified state.

Starting with Windows 8, the operating system calls this function during a bugcheck operation following a system stop error.


## -prototype


````
DXGKDDI_SYSTEM_DISPLAY_ENABLE DxgkDdiSystemDisplayEnable;

_Check_return_ NTSTATUS* DxgkDdiSystemDisplayEnable(
  _In_  PVOID                                MiniportDeviceContext,
  _In_  D3DDDI_VIDEO_PRESENT_TARGET_ID       TargetId,
  _In_  PDXGKARG_SYSTEM_DISPLAY_ENABLE_FLAGS Flags,
  _Out_ UINT                                 *Width,
  _Out_ UINT                                 *Height,
  _Out_ D3DDDIFORMAT                         *ColorFormat
)
{ ... }
````


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem.




### -param TargetId [in]

A D3DDDI_VIDEO_PRESENT_TARGET_ID value that specifies the identifier of the video present target on the display adapter that the display device is connected to. This identifier could be for the target that was left in the current video present network (VidPn) state during the previous call to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_commitvidpn.md">DxgkDdiCommitVidPn</a>.

For more details about the use of the <i>TargetId</i> parameter, see the following "Video present target initialization" section.


### -param Flags [in]

A pointer to a value that contains a bitwise OR of flags. This member is reserved by the operating system.


### -param Width [out]

A UINT value that specifies the width of the display mode of the specified device in units of pixels.


### -param Height [out]

A UINT value that specifies the height of the display mode  of the specified device in units of pixels.


### -param ColorFormat [out]

A pointer to a <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a> value that specifies the color format of the display device.


## -returns



<i>DxgkDdiSystemDisplayEnable</i> returns STATUS_SUCCESS if it succeeds. If the target specified by the TargetId parameter is not connected to a display device, the function returns STATUS_NOT_SUPPORTED. Otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



<h3><a id="Required_steps_by_display_miniport_driver"></a><a id="required_steps_by_display_miniport_driver"></a><a id="REQUIRED_STEPS_BY_DISPLAY_MINIPORT_DRIVER"></a>Required steps by display miniport driver</h3>
The display miniport driver must follow these steps when its <i>DxgkDdiSystemDisplayEnable</i> function is called:

<ol>
<li>The driver must cancel all graphics processing unit (GPU) operations or reset the GPU to the idle state.</li>
<li>The operating system indicates the video present target through the <i>TargetId</i> parameter. The driver  must keep the display associated with this target powered on and visible. If the driver cannot power on the display, it must fail the call to this function. In such a failure case, the operating system might call the <a href="..\dispmprt\nc-dispmprt-dxgkddi_reset_device.md">DxgkDdiResetDevice</a> function and cause a system bugcheck to occur.</li>
<li>The driver must check the connectivity of the display associated with this target. If the target does not have a display connected, the driver must complete the call to this function and return the <b>STATUS_NOT_SUPPORTED</b> error code.</li>
<li>The driver must disable the signal to all other displays that are connected to the display adapter. If this is not possible, the driver should attempt to place a blank image on all other displays. If this is not possible, the driver must leave the last image on the screen unchanged.</li>
<li>The driver must keep the current display mode on the indicated target and provide this mode back to the operating system as part of this function call.</li>
<li>
If the driver cannot maintain the current display mode, or if the target is not part of the active topology, the driver should attempt to set a frame buffer on another target that is capable of a display resolution of at least 640 x 480 pixels in a format of 24 bits per pixel. If that is not possible, the driver can fail this function call, which will result in a system bugcheck and the display of a black screen.

It is not required that the driver use a linear frame buffer mode. However, the driver should support write operations to this frame buffer from sources that have the  <b>D3DDDIFMT_A8R8G8B8</b> format of the <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a> enumeration.

</li>
</ol>
<h3><a id="Source_image_restrictions"></a><a id="source_image_restrictions"></a><a id="SOURCE_IMAGE_RESTRICTIONS"></a>Source image restrictions</h3>
After the driver gives the operating system control over display  functionality, the operating system can call the <a href="..\dispmprt\nc-dispmprt-dxgkddi_system_display_write.md">DxgkDdiSystemDisplayWrite</a> function to update the screen image and to write a block of images from specified sources to the screen that was reset by the <i>DxgkDdiSystemDisplayEnable</i> function.


<a href="..\dispmprt\nc-dispmprt-dxgkddi_system_display_write.md">DxgkDdiSystemDisplayWrite</a> provides the driver with the starting address of the source image as well as the stride, width, and height. The color format of the source image is always <b>D3DDDIFMT_X8R8G8B8</b>. The operating system guarantees that the source image is in non-paged memory.

The  driver must write this source image to the current screen starting at the positions specified by the <i>PositionX</i> and <i>PositionY</i> parameters of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_system_display_write.md">DxgkDdiSystemDisplayWrite</a> function.

It is recommended that the driver use the CPU to write the image from the source to the frame buffer because a system bugcheck might be caused by repeated <a href="https://msdn.microsoft.com/f410eec7-026f-41e0-8c60-72f651659ead">Timeout Detection and Recovery (TDR)</a> instances that result in the GPU being in an unknown condition.

<h3><a id="Use_non-paged_memory"></a><a id="use_non-paged_memory"></a><a id="USE_NON-PAGED_MEMORY"></a>Use non-paged memory</h3>
Windows kernel-mode functions might not be available while this function is being called.

<i>DxgkDdiSystemDisplayEnable</i> can be called at any IRQL, so it must be in nonpageable memory. <i>DxgkDdiSystemDisplayEnable</i> must not call any code that is in pageable memory and must not manipulate any data that is in pageable memory.




## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_system_display_write.md">DxgkDdiSystemDisplayWrite</a>



<a href="https://msdn.microsoft.com/6454adb3-c958-467b-acbc-b8937b98cd57">DxgkCbAcquirePostDisplayOwnership</a>



<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_reset_device.md">DxgkDdiResetDevice</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_stop_device_and_release_post_display_ownership.md">DxgkDdiStopDeviceAndReleasePostDisplayOwnership</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_SYSTEM_DISPLAY_ENABLE callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

