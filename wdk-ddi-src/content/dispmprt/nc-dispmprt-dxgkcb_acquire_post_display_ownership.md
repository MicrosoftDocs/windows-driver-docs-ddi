---
UID: NC:dispmprt.DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP
title: DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP (dispmprt.h)
description: Called by a Windows Display Driver Model (WDDM) 1.2 or later display miniport driver to obtain the display information from the current power-on self-test (POST) display device or the previously running WDDM driver.
old-location: display\DxgkCbAcquirePostDisplayOwnership.htm
tech.root: display
ms.assetid: 6454adb3-c958-467b-acbc-b8937b98cd57
ms.date: 05/10/2018
ms.keywords: DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP, DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP callback, DxgkCbAcquirePostDisplayOwnership, DxgkCbAcquirePostDisplayOwnership callback function [Display Devices], display.DxgkCbAcquirePostDisplayOwnership, dispmprt/DxgkCbAcquirePostDisplayOwnership
ms.topic: callback
f1_keywords:
 - "dispmprt/DxgkCbAcquirePostDisplayOwnership"
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- dispmprt.h
api_name:
- DxgkCbAcquirePostDisplayOwnership
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP callback function


## -description


Called by a Windows Display Driver Model (WDDM) 1.2 or later display miniport driver to obtain the display information from the current  power-on self-test (POST) display device or the previously running WDDM driver.

 The driver must use this display information to optimize the initial mode change request after the display device has been started.


## -parameters




### -param DeviceHandle [in]

A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgkrnl_interface">DXGKRNL_INTERFACE</a> structure that was passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a>.


### -param DisplayInfo [out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgk_display_information">DXGK_DISPLAY_INFORMATION</a> structure that is allocated by the display miniport driver. If <i>DxgkCbAcquirePostDisplayOwnership</i> returns STATUS_SUCCESS, this structure contains display information for the current display device that is used for POST operations.


## -returns



<i>DxgkCbAcquirePostDisplayOwnership</i> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



<h3><a id="Allowed_color_formats"></a><a id="allowed_color_formats"></a><a id="ALLOWED_COLOR_FORMATS"></a>Allowed color formats</h3>
The <i>DisplayInfo</i>-><b>ColorFormat</b> member must include a bitwise-OR combination of the following two formats:

<ul>
<li><b>D3DDDIFMT_X8R8G8B8</b></li>
<li><b>D3DDDIFMT_A8R8G8B8</b></li>
</ul>
If the operating system reports back the <b>D3DDDIFMT_R8G8B8</b> format, the display miniport driver should ignore it.

<h3><a id="Video_present_target_initialization"></a><a id="video_present_target_initialization"></a><a id="VIDEO_PRESENT_TARGET_INITIALIZATION"></a>Video present target initialization</h3>
It is possible that the <i>DisplayInfo</i>-><b>TargetId</b> member is not initialized. In this case, the identifier of the video present target is <b>D3DDDI_ID_UNINITIALIZED</b>. Typically, this occurs after a system boot.

Similarly, it is possible that the <i>DisplayInfo</i>-><b>AcpiId</b> member is not initialized. In this case, the ACPI identifier <b>AcpiId</b> has a value of zero.

In the case of a driver-to-driver upgrade, the previous driver will have provided the target identifier and the ACPI identifier.

<h3><a id="Implementation_guidelines"></a><a id="implementation_guidelines"></a><a id="IMPLEMENTATION_GUIDELINES"></a>Implementation guidelines</h3>
Starting with WDDM 1.2, the display miniport driver must follow these guidelines when it calls <i>DxgkCbAcquirePostDisplayOwnership</i>:

<ul>
<li>
The entry point for the <i>DxgkCbAcquirePostDisplayOwnership</i> function is part of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgkrnl_interface">DXGKRNL_INTERFACE</a> structure. This structure is returned to the driver through the  <i>DxgkInterface</i> parameter when the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a> function is called.

</li>
<li>
	It is optional for the display miniport driver to call <i>DxgkCbAcquirePostDisplayOwnership</i>. However, the operating system might still call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_stop_device_and_release_post_display_ownership">DxgkDdiStopDeviceAndReleasePostDisplayOwnership</a> function of the device driver if the driver did not previously call <i>DxgkCbAcquirePostDisplayOwnership</i>.

</li>
<li>The display miniport driver can call <i>DxgkCbAcquirePostDisplayOwnership</i> if the device is started in response to a Plug and Play (PnP) event. In this case, the driver must call <i>DxgkCbAcquirePostDisplayOwnership</i> from within the context of the call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a> function.</li>
<li>The display miniport driver can call <i>DxgkCbAcquirePostDisplayOwnership</i> if the device resumes a <b>PowerDeviceD0</b> power state after a hibernation state. In this case, the driver must call <i>DxgkCbAcquirePostDisplayOwnership</i> from within the context of the call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_set_power_state">DxgkDdiSetPowerState</a> function.</li>
<li>
The display miniport driver must only call the <i>DxgkCbAcquirePostDisplayOwnership</i> function if the driver is running under Windows 8 or a later version of the Windows operating system.

<div class="alert"><b>Note</b>  The display miniport driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlgetversion">RtlGetVersion</a> to determine the version of the operating system.</div>
<div> </div>
</li>
<li>
<i>DxgkCbAcquirePostDisplayOwnership</i> may return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgk_display_information">DXGK_DISPLAY_INFORMATION</a> structure with the <b>Width</b> member set to zero. This indicates that either the  current display device is not capable of POST operations or the operating system does not have the current display information for the current POST device.

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgkrnl_interface">DXGKRNL_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgk_display_information">DXGK_DISPLAY_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_set_power_state">DxgkDdiSetPowerState</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_stop_device_and_release_post_display_ownership">DxgkDdiStopDeviceAndReleasePostDisplayOwnership</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlgetversion">RtlGetVersion</a>
 

 

