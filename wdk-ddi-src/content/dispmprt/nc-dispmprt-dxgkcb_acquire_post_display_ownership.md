---
UID: NC:dispmprt.DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP
title: DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP
author: windows-driver-content
description: Called by a Windows Display Driver Model (WDDM) 1.2 or later display miniport driver to obtain the display information from the current power-on self-test (POST) display device or the previously running WDDM driver.
old-location: display\DxgkCbAcquirePostDisplayOwnership.htm
old-project: display
ms.assetid: 6454adb3-c958-467b-acbc-b8937b98cd57
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP, DxgkCbAcquirePostDisplayOwnership, DxgkCbAcquirePostDisplayOwnership callback function [Display Devices], display.DxgkCbAcquirePostDisplayOwnership, dispmprt/DxgkCbAcquirePostDisplayOwnership
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	dispmprt.h
apiname:
-	DxgkCbAcquirePostDisplayOwnership
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP callback


## -description


Called by a Windows Display Driver Model (WDDM) 1.2 or later display miniport driver to obtain the display information from the current  power-on self-test (POST) display device or the previously running WDDM driver.

 The driver must use this display information to optimize the initial mode change request after the display device has been started.


## -prototype


````
DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP DxgkCbAcquirePostDisplayOwnership;

NTSTATUS APIENTRY* DxgkCbAcquirePostDisplayOwnership(
  _In_  HANDLE                   DeviceHandle,
  _Out_ DXGK_DISPLAY_INFORMATION *DisplayInfo
)
{ ... }
````


## -parameters




### -param DeviceHandle [in]

A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure that was passed to <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>.


### -param DisplayInfo [out]

A pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_display_information.md">DXGK_DISPLAY_INFORMATION</a> structure that is allocated by the display miniport driver. If <i>DxgkCbAcquirePostDisplayOwnership</i> returns STATUS_SUCCESS, this structure contains display information for the current display device that is used for POST operations.


## -returns



<i>DxgkCbAcquirePostDisplayOwnership</i> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



<h3><a id="Allowed_color_formats"></a><a id="allowed_color_formats"></a><a id="ALLOWED_COLOR_FORMATS"></a>Allowed color formats</h3>
The <i>DisplayInfo</i>-&gt;<b>ColorFormat</b> member must include a bitwise-OR combination of the following two formats:

<ul>
<li><b>D3DDDIFMT_X8R8G8B8</b></li>
<li><b>D3DDDIFMT_A8R8G8B8</b></li>
</ul>
If the operating system reports back the <b>D3DDDIFMT_R8G8B8</b> format, the display miniport driver should ignore it.

<h3><a id="Video_present_target_initialization"></a><a id="video_present_target_initialization"></a><a id="VIDEO_PRESENT_TARGET_INITIALIZATION"></a>Video present target initialization</h3>
It is possible that the <i>DisplayInfo</i>-&gt;<b>TargetId</b> member is not initialized. In this case, the identifier of the video present target is <b>D3DDDI_ID_UNINITIALIZED</b>. Typically, this occurs after a system boot.

Similarly, it is possible that the <i>DisplayInfo</i>-&gt;<b>AcpiId</b> member is not initialized. In this case, the ACPI identifier <b>AcpiId</b> has a value of zero.

In the case of a driver-to-driver upgrade, the previous driver will have provided the target identifier and the ACPI identifier.

<h3><a id="Implementation_guidelines"></a><a id="implementation_guidelines"></a><a id="IMPLEMENTATION_GUIDELINES"></a>Implementation guidelines</h3>
Starting with WDDM 1.2, the display miniport driver must follow these guidelines when it calls <i>DxgkCbAcquirePostDisplayOwnership</i>:

<ul>
<li>
The entry point for the <i>DxgkCbAcquirePostDisplayOwnership</i> function is part of the <a href="..\dispmprt\ns-dispmprt-_dxgkrnl_interface.md">DXGKRNL_INTERFACE</a> structure. This structure is returned to the driver through the  <i>DxgkInterface</i> parameter when the driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a> function is called.

</li>
<li>
	It is optional for the display miniport driver to call <i>DxgkCbAcquirePostDisplayOwnership</i>. However, the operating system might still call the <a href="..\dispmprt\nc-dispmprt-dxgkddi_stop_device_and_release_post_display_ownership.md">DxgkDdiStopDeviceAndReleasePostDisplayOwnership</a> function of the device driver if the driver did not previously call <i>DxgkCbAcquirePostDisplayOwnership</i>.

</li>
<li>The display miniport driver can call <i>DxgkCbAcquirePostDisplayOwnership</i> if the device is started in response to a Plug and Play (PnP) event. In this case, the driver must call <i>DxgkCbAcquirePostDisplayOwnership</i> from within the context of the call to the <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a> function.</li>
<li>The display miniport driver can call <i>DxgkCbAcquirePostDisplayOwnership</i> if the device resumes a <b>PowerDeviceD0</b> power state after a hibernation state. In this case, the driver must call <i>DxgkCbAcquirePostDisplayOwnership</i> from within the context of the call to the <a href="..\dispmprt\nc-dispmprt-dxgkddi_set_power_state.md">DxgkDdiSetPowerState</a> function.</li>
<li>
The display miniport driver must only call the <i>DxgkCbAcquirePostDisplayOwnership</i> function if the driver is running under Windows 8 or a later version of the Windows operating system.

<div class="alert"><b>Note</b>  The display miniport driver can call <a href="..\wdm\nf-wdm-rtlgetversion.md">RtlGetVersion</a> to determine the version of the operating system.</div>
<div> </div>
</li>
<li>
<i>DxgkCbAcquirePostDisplayOwnership</i> may return a <a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_display_information.md">DXGK_DISPLAY_INFORMATION</a> structure with the <b>Width</b> member set to zero. This indicates that either the  current display device is not capable of POST operations or the operating system does not have the current display information for the current POST device.

</li>
</ul>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>



<a href="..\wdm\nf-wdm-rtlgetversion.md">RtlGetVersion</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_set_power_state.md">DxgkDdiSetPowerState</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_display_information.md">DXGK_DISPLAY_INFORMATION</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_stop_device_and_release_post_display_ownership.md">DxgkDdiStopDeviceAndReleasePostDisplayOwnership</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

