---
UID: NC:dispmprt.DXGKDDI_SYSTEM_DISPLAY_ENABLE
title: DXGKDDI_SYSTEM_DISPLAY_ENABLE (dispmprt.h)
description: Called by the operating system to request the display miniport driver to reset the current display device to a specified state.
old-location: display\dxgkddisystemdisplayenable.htm
tech.root: display
ms.assetid: D938F7F4-E1FA-4C63-A31D-5ED160276565
ms.date: 05/10/2018
ms.keywords: DXGKDDI_SYSTEM_DISPLAY_ENABLE, DXGKDDI_SYSTEM_DISPLAY_ENABLE callback, DxgkDdiSystemDisplayEnable, DxgkDdiSystemDisplayEnable callback function [Display Devices], display.dxgkddisystemdisplayenable, dispmprt/DxgkDdiSystemDisplayEnable
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- dispmprt.h
api_name:
- DxgkDdiSystemDisplayEnable
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_SYSTEM_DISPLAY_ENABLE callback function


## -description


Called by the operating system to request the display miniport driver to reset the current  display device to a specified state.

Starting with Windows 8, the operating system calls this function during a bugcheck operation following a system stop error.


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem.




### -param TargetId [in]

A D3DDDI_VIDEO_PRESENT_TARGET_ID value that specifies the identifier of the video present target on the display adapter that the display device is connected to. This identifier could be for the target that was left in the current video present network (VidPn) state during the previous call to <a href="https://msdn.microsoft.com/979b86e9-f3ff-4022-8c00-b6afc2b1f747">DxgkDdiCommitVidPn</a>.

For more details about the use of the <i>TargetId</i> parameter, see the following "Video present target initialization" section.


### -param Flags [in]

A pointer to a value that contains a bitwise OR of flags. This member is reserved by the operating system.


### -param Width [out]

A UINT value that specifies the width of the display mode of the specified device in units of pixels.


### -param Height [out]

A UINT value that specifies the height of the display mode  of the specified device in units of pixels.


### -param ColorFormat [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a> value that specifies the color format of the display device.


## -returns



<i>DxgkDdiSystemDisplayEnable</i> returns STATUS_SUCCESS if it succeeds. If the target specified by the TargetId parameter is not connected to a display device, the function returns STATUS_NOT_SUPPORTED. Otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



<h3><a id="Required_steps_by_display_miniport_driver"></a><a id="required_steps_by_display_miniport_driver"></a><a id="REQUIRED_STEPS_BY_DISPLAY_MINIPORT_DRIVER"></a>Required steps by display miniport driver</h3>
The display miniport driver must follow these steps when its <i>DxgkDdiSystemDisplayEnable</i> function is called:

<ol>
<li>The driver must cancel all graphics processing unit (GPU) operations or reset the GPU to the idle state.</li>
<li>The operating system indicates the video present target through the <i>TargetId</i> parameter. The driver  must keep the display associated with this target powered on and visible. If the driver cannot power on the display, it must fail the call to this function. In such a failure case, the operating system might call the <a href="https://msdn.microsoft.com/e757e63d-6d78-4b20-9471-290f56c1bcde">DxgkDdiResetDevice</a> function and cause a system bugcheck to occur.</li>
<li>The driver must check the connectivity of the display associated with this target. If the target does not have a display connected, the driver must complete the call to this function and return the <b>STATUS_NOT_SUPPORTED</b> error code.</li>
<li>The driver must disable the signal to all other displays that are connected to the display adapter. If this is not possible, the driver should attempt to place a blank image on all other displays. If this is not possible, the driver must leave the last image on the screen unchanged.</li>
<li>The driver must keep the current display mode on the indicated target and provide this mode back to the operating system as part of this function call.</li>
<li>
If the driver cannot maintain the current display mode, or if the target is not part of the active topology, the driver should attempt to set a frame buffer on another target that is capable of a display resolution of at least 640 x 480 pixels in a format of 24 bits per pixel. If that is not possible, the driver can fail this function call, which will result in a system bugcheck and the display of a black screen.

It is not required that the driver use a linear frame buffer mode. However, the driver should support write operations to this frame buffer from sources that have the  <b>D3DDDIFMT_A8R8G8B8</b> format of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a> enumeration.

</li>
</ol>
<h3><a id="Source_image_restrictions"></a><a id="source_image_restrictions"></a><a id="SOURCE_IMAGE_RESTRICTIONS"></a>Source image restrictions</h3>
After the driver gives the operating system control over display  functionality, the operating system can call the <a href="https://msdn.microsoft.com/5C0F9878-522C-4DDE-A790-54C94880F119">DxgkDdiSystemDisplayWrite</a> function to update the screen image and to write a block of images from specified sources to the screen that was reset by the <i>DxgkDdiSystemDisplayEnable</i> function.


<a href="https://msdn.microsoft.com/5C0F9878-522C-4DDE-A790-54C94880F119">DxgkDdiSystemDisplayWrite</a> provides the driver with the starting address of the source image as well as the stride, width, and height. The color format of the source image is always <b>D3DDDIFMT_X8R8G8B8</b>. The operating system guarantees that the source image is in non-paged memory.

The  driver must write this source image to the current screen starting at the positions specified by the <i>PositionX</i> and <i>PositionY</i> parameters of the <a href="https://msdn.microsoft.com/5C0F9878-522C-4DDE-A790-54C94880F119">DxgkDdiSystemDisplayWrite</a> function.

It is recommended that the driver use the CPU to write the image from the source to the frame buffer because a system bugcheck might be caused by repeated <a href="https://msdn.microsoft.com/f410eec7-026f-41e0-8c60-72f651659ead">Timeout Detection and Recovery (TDR)</a> instances that result in the GPU being in an unknown condition.

<h3><a id="Use_non-paged_memory"></a><a id="use_non-paged_memory"></a><a id="USE_NON-PAGED_MEMORY"></a>Use non-paged memory</h3>
Windows kernel-mode functions might not be available while this function is being called.

<i>DxgkDdiSystemDisplayEnable</i> can be called at any IRQL, so it must be in nonpageable memory. <i>DxgkDdiSystemDisplayEnable</i> must not call any code that is in pageable memory and must not manipulate any data that is in pageable memory.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a>



<a href="https://msdn.microsoft.com/6454adb3-c958-467b-acbc-b8937b98cd57">DxgkCbAcquirePostDisplayOwnership</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>



<a href="https://msdn.microsoft.com/e757e63d-6d78-4b20-9471-290f56c1bcde">DxgkDdiResetDevice</a>



<a href="https://msdn.microsoft.com/6AF170BF-C422-4340-8935-31A4D4F3EFA5">DxgkDdiStopDeviceAndReleasePostDisplayOwnership</a>



<a href="https://msdn.microsoft.com/5C0F9878-522C-4DDE-A790-54C94880F119">DxgkDdiSystemDisplayWrite</a>
 

 

