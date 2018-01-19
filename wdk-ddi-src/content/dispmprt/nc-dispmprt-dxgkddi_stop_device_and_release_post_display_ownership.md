---
UID: NC:dispmprt.DXGKDDI_STOP_DEVICE_AND_RELEASE_POST_DISPLAY_OWNERSHIP
title: DXGKDDI_STOP_DEVICE_AND_RELEASE_POST_DISPLAY_OWNERSHIP
author: windows-driver-content
description: Called by the operating system to request the display miniport driver to reset the display device and to release ownership of the current power-on self-test (POST) device.
old-location: display\dxgkddireleasepostdisplayownership.htm
old-project: display
ms.assetid: 6AF170BF-C422-4340-8935-31A4D4F3EFA5
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _SYMBOL_INFO_EX, *PSYMBOL_INFO_EX, SYMBOL_INFO_EX
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
req.alt-api: DxgkDdiStopDeviceAndReleasePostDisplayOwnership
req.alt-loc: dispmprt.h
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
req.typenames: *PSYMBOL_INFO_EX, SYMBOL_INFO_EX
---

# DXGKDDI_STOP_DEVICE_AND_RELEASE_POST_DISPLAY_OWNERSHIP callback



## -description
Called by the operating system to request the display miniport driver to reset the  display device and to release ownership of the current  power-on self-test (POST)  device.

Starting with Windows 8, the operating system calls this function during a Plug and Play (PnP) stop operation.

To indicate to the operating system that this function is supported, the driver must set the <b>NonVGASupport</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a> structure when the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> function is called.



## -prototype

````
DXGKDDI_STOP_DEVICE_AND_RELEASE_POST_DISPLAY_OWNERSHIP DxgkDdiStopDeviceAndReleasePostDisplayOwnership;

NTSTATUS DxgkDdiStopDeviceAndReleasePostDisplayOwnership(
  _In_  PVOID                          MiniportDeviceContext,
  _In_  D3DDDI_VIDEO_PRESENT_TARGET_ID TargetId,
  _Out_ PDXGK_DISPLAY_INFORMATION      DisplayInfo
)
{ ... }
````


## -parameters

### -param MiniportDeviceContext [in]

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem.




### -param TargetId [in]

A <b>D3DDDI_VIDEO_PRESENT_TARGET_ID</b> value that specifies the identifier of the video present target on the display adapter that the display device is connected to. This identifier could be for the target that was left in the current video present network (VidPN) state during the previous call to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_commitvidpn.md">DxgkDdiCommitVidPn</a>.

For more details about the use of the <i>TargetId</i> parameter, see the following Remarks section.


### -param DisplayInfo [out]

A pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_display_information.md">DXGK_DISPLAY_INFORMATION</a> structure that is allocated by the operating system.


## -returns
Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes defined in Ntstatus.h. For more information, see the following Remarks section.


## -remarks
The display miniport driver should report only a 32-bit color format. Therefore the <i>DisplayInfo</i>-&gt;<b>ColorFormat</b> member must include only one of the following two formats:

The display miniport driver must set the <i>DisplayInfo</i>-&gt;<b>TargetId</b> member to the target identifier of the display that remains active. Typically, this identifier will be the value of the <i>TargetId</i> parameter that the operating system passed to the driver.

Similarly, the display miniport driver must set the <i>DisplayInfo</i>-&gt;<b>AcpiId</b> member to the ACPI identifier of the display that remains active.

The display miniport driver must follow these steps when its <i>DxgkDdiStopDeviceAndReleasePostDisplayOwnership</i> function is called:

The driver must stop the display device associated with the video present target indicated by the <i>TargetId</i> parameter but must keep the display associated with this target powered on and visible.

If the driver cannot maintain the current display mode, or if the target is not part of the active topology, the driver should select an alternate active target and attempt to maintain the current resolution of that target. If that is not possible, the driver should attempt to set the display to its native resolution or to a high-resolution mode. In this case, the  display resolution must be set to at least 800 x 600 pixels in either <b>D3DDDIFMT_R8G8B8</b> (24 bits per pixel) or <b>D3DDDIFMT_X8R8G8B8</b> (32 bpp) color formats of the <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a> enumeration.

If possible, the driver must	clear the current frame buffer and disable the hardware cursor and all display overlays.

If possible, the driver must set the gamma ramp of the device to its default values.

The driver must 	set the current frame buffer to be in a linear mode. The driver does this either by using the default swizzle range or by disabling swizzle mode.

	The driver must make the current frame buffer accessible to the CPU by mapping the  current frame buffer linearly into the CPU address space.

After the display miniport driver performs these steps, it must return the current display settings for the device. The driver returns this information by setting the members of the <a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_display_information.md">DXGK_DISPLAY_INFORMATION</a> structure that is referenced by the <i>DisplayInfo</i> parameter.

On systems that support the Unified Extensible Firmware Interface (UEFI), a VGA basic input/output system (BIOS) does not exist. To support PnP stop operations on these systems, Windows Display Driver Model (WDDM) 1.2 and later provides support for the operating system to reset the POST device and to get its display information during a PnP stop operation.  The operating system does this by calling the display miniport driver's <i>DxgkDdiStopDeviceAndReleasePostDisplayOwnership</i> function.

 A PnP stop operation can occur in response to requests by processes such as the Device Manager, or during a driver upgrade process.

Starting with Windows 8, the operating system calls the driver's <i>DxgkDdiStopDeviceAndReleasePostDisplayOwnership</i> function only on the POST device during a PnP stop operation.

If the driver successfully completes a call to this function, the operating system will not call the <a href="..\dispmprt\nc-dispmprt-dxgkddi_stop_device.md">DxgkDdiStopDevice</a> function. If the driver fails to complete a call to this function, the operating system will call the <i>DxgkDdiStopDevice</i> function, and device behavior will be the same as in Windows 7.

On UEFI-only systems, if the display miniport driver fails a call to this function, a black screen is displayed and the IHV driver is not installed. The workaround to this scenario is for the user to reboot the computer.

For more information on how this function is used in PnP scenarios, see <a href="https://msdn.microsoft.com/A95DCFEA-BC1B-4A13-9850-13814725D53E">Plug and Play (PnP) in WDDM 1.2 and later</a>.


## -see-also
<dl>
<dt>
<a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_display_information.md">DXGK_DISPLAY_INFORMATION</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/6454adb3-c958-467b-acbc-b8937b98cd57">DxgkCbAcquirePostDisplayOwnership</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_stop_device.md">DxgkDdiStopDevice</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_STOP_DEVICE_AND_RELEASE_POST_DISPLAY_OWNERSHIP callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

