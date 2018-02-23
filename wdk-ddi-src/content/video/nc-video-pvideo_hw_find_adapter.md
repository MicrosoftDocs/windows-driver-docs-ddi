---
UID: NC:video.PVIDEO_HW_FIND_ADAPTER
title: PVIDEO_HW_FIND_ADAPTER
author: windows-driver-content
description: HwVidFindAdapter performs initialization of data specific to the miniport driver and devices supported by the miniport driver.
old-location: display\hwvidfindadapter.htm
old-project: display
ms.assetid: 8c880eff-4b4c-439e-9239-f2343c1fe084
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: display.hwvidfindadapter, HwVidFindAdapter callback function [Display Devices], HwVidFindAdapter, PVIDEO_HW_FIND_ADAPTER, PVIDEO_HW_FIND_ADAPTER, video/HwVidFindAdapter, VideoMiniport_Functions_f035d610-08b2-4403-b9dc-c069520d61bb.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	video.h
apiname:
-	HwVidFindAdapter
product: Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---

# PVIDEO_HW_FIND_ADAPTER callback


## -description


<i>HwVidFindAdapter</i> performs initialization of data specific to the miniport driver and devices supported by the miniport driver.


## -prototype


````
PVIDEO_HW_FIND_ADAPTER HwVidFindAdapter;

VP_STATUS HwVidFindAdapter(
   PVOID                   HwDeviceExtension,
   PVOID                   HwContext,
   PWSTR                   ArgumentString,
   PVIDEO_PORT_CONFIG_INFO ConfigInfo,
   PUCHAR                  Again
)
{ ... }
````


## -parameters




### -param HwDeviceExtension

Pointer to the driver's per-device storage area. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543119">Device Extensions</a>.


### -param HwContext

Is <b>NULL</b> and should be ignored by the miniport driver.


### -param ArgumentString

Pointer to a null-terminated ASCII string that originates with the user. This pointer can be <b>NULL</b>.


### -param ConfigInfo

Pointer to a <a href="..\video\ns-video-_video_port_config_info.md">VIDEO_PORT_CONFIG_INFO</a> structure. The video port driver allocates memory for and initializes this structure with any known configuration information, such as the system IO bus number and values that the miniport driver set in the <a href="..\video\ns-video-_video_hw_initialization_data.md">VIDEO_HW_INITIALIZATION_DATA</a> structure.


### -param Again

Should be ignored by the miniport driver.


## -returns



<i>HwVidFindAdapter</i> must return one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>ERROR_DEV_NOT_EXIST</b></dt>
</dl>
</td>
<td width="60%">
Indicates, for a reenumerable bus, that the miniport driver could not find the device.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>ERROR_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Indicates the miniport driver could not configure or initialize the adapter successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NO_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Indicates success.

</td>
</tr>
</table>
 




## -remarks



Every video miniport driver must have an <i>HwVidFindAdapter</i> function.

The video port driver does the following before it calls <i>HwVidFindAdapter</i>:

<ul>
<li>
Allocates storage for the miniport driver's per-adapter storage area according to the value of <b>HwDeviceExtensionSize</b> that the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> function specified in the <a href="..\video\ns-video-_video_hw_initialization_data.md">VIDEO_HW_INITIALIZATION_DATA</a> structure, and zero-initializes the allocated storage.

</li>
<li>
Allocates storage for a <a href="..\video\ns-video-_video_port_config_info.md">VIDEO_PORT_CONFIG_INFO</a> structure and fills in all available information based on miniport driver-supplied information in VIDEO_HW_INITIALIZATION_DATA.

</li>
</ul>
The video port driver then calls the miniport driver's <i>HwVidFindAdapter</i> function with pointers to the initialized per-adapter storage area and configuration information in the <i>HwDeviceExtension</i> and <i>ConfigInfo</i> parameters, respectively.

The <i>HwVidFindAdapter</i> function for devices on an enumerable bus must do the following:

<ul>
<li>
Check the size of the VIDEO_PORT_CONFIG_INFO structure to which <i>ConfigInfo</i> points to ensure proper versioning.

</li>
<li>
Call <b>VideoPortGetAccessRanges</b> to obtain the bus-relative physical addresses to which the device will respond. These addresses are assigned by the PnP manager. The miniport driver should pass <b>NULL</b> in the <i>VendorId</i>, <i>DeviceId</i>, and <i>Slot</i> parameters of <b>VideoPortGetAccessRanges</b>.

</li>
<li>
For miniport drivers that support several device types, determine the type of device that the PnP manager has detected. The miniport driver can call <b>VideoPortGetBusData</b> to obtain PCI configuration information.

</li>
<li>
Fill in any relevant but missing configuration information in the appropriate members of the VIDEO_PORT_CONFIG_INFO structure with adapter-specific data.

</li>
</ul>
<i>HwVidFindAdapter</i> should not attempt to initialize the device.

<i>HwVidFindAdapter</i> can allocate resources, such as memory and locks, for use by the miniport driver. Those resources can be device-specific or they can be shared by several devices that the miniport driver supports. If <i>HwVidFindAdapter</i> returns any value other than NO_ERROR, it must free all device-specific resources before returning. For resources that are shared among several devices, <i>HwVidFindAdapter</i> should keep a reference count. For example, the reference count could indicate the number of previous calls to <i>HwVidFindAdapter</i> that succeeded. That way, if <i>HwVidFindAdapter</i> must fail, and it determines that all previous calls to <i>HwVidFindAdapter</i> have failed, it could free the shared resources.

If <i>HwVidFindAdapter</i> fails every time it is called by the video port driver, the operating system might unload the miniport driver later. In such a case, any resources that <i>HwVidFindAdapter</i> allocated but did not free will leak.

For a device on a reenumerable bus such as ISA, PnP still attempts to start the device, although it is the responsibility of <i>HwVidFindAdapter</i> to determine whether the device is actually present. If the device is not found, <i>HwVidFindAdapter</i> should return ERROR_DEV_NOT_EXIST.

<i>HwVidFindAdapter</i> should also call <b>VideoPortSetRegistryParameters</b> to store adapter-specific information in the <b>HardwareInformation</b> key. This information is used by the Display program in Control Panel. See <a href="https://msdn.microsoft.com/82f5d399-58c3-4bed-a3f2-3501f21fa3e8">Setting Hardware Information in the Registry</a> for details.

Depending on the adapter and the <b>AdapterInterfaceType</b> value in <a href="..\video\ns-video-_video_port_config_info.md">VIDEO_PORT_CONFIG_INFO</a>, <i>HwVidFindAdapter</i> can call some of the following <b>VideoPort</b><i>Xxx</i> functions to get the necessary bus-relative configuration data and mapped access ranges to communicate with the adapter:

<ul>
<li>

<a href="..\video\nf-video-videoportgetbusdata.md">VideoPortGetBusData</a> to get bus-type-specific configuration information about an adapter on a particular I/O bus.

</li>
<li>

<a href="..\video\nf-video-videoportgetdevicedata.md">VideoPortGetDeviceData</a> to get VIDEO_DEVICE_DATA_TYPE-specific information from the registry and call <a href="..\video\nc-video-pminiport_query_device_routine.md">HwVidQueryDeviceCallback</a> to process this information.

</li>
<li>

<a href="..\video\nf-video-videoportgetregistryparameters.md">VideoPortGetRegistryParameters</a> to get configuration information from the registry.

</li>
<li>

<a href="..\video\nf-video-videoportgetaccessranges.md">VideoPortGetAccessRanges</a> to get bus-relative access ranges addresses and possibly other hardware configuration values, and to claim them in the registry for use by the driver of an adapter.

</li>
<li>

<a href="..\video\nf-video-videoportverifyaccessranges.md">VideoPortVerifyAccessRanges</a> to determine whether bus-relative video memory and/or I/O ports for the adapter can be claimed by the miniport driver; otherwise, a previously loaded driver has already claimed the resource in the registry and <i>HwVidFindAdapter</i> must try to claim other access ranges if possible or fail.

</li>
<li>

<a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a> to map each successfully claimed bus-relative base address and range size, as described in a <a href="..\video\ns-video-_video_access_range.md">VIDEO_ACCESS_RANGE</a> structure, to <a href="https://msdn.microsoft.com/5f6fec1a-1134-4765-81be-9b50939e5e66">system space</a> logical addresses. <i>HwVidFindAdapter</i> must successfully call <b>VideoPortVerifyAccessRanges</b> or <b>VideoPortGetAccessRanges</b> before it can call <b>VideoPortGetDeviceBase</b>.

</li>
</ul>
If the driver does not handle interrupts, <i>HwVidFindAdapter</i> should set both <b>BusInterruptLevel</b> and <b>BusInterruptVector</b> in the VIDEO_PORT_CONFIG_INFO structure to zero after its call to <b>VideoPortGetAccessRanges</b>. If both members are zero, the video port driver does not connect the interrupt for the miniport driver. Explicitly setting both <b>BusInterruptLevel</b> and <b>BusInterruptVector</b> to zero in <i>HwVidFindAdapter</i> disables the <a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a> entry point, if any, that was set up by the miniport driver's <b>DriverEntry</b> routine.

<i>HwVidFindAdapter</i> must not leave an unsupported adapter with its state changed. For VGA/SVGA adapters, <i>HwVidFindAdapter</i> must leave the adapter in a VGA state and restore any extended registers it might have modified to their original condition.

<i>HwVidFindAdapter</i> should be made pageable.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556178">DrvAssertMode</a>



<a href="..\video\ns-video-_video_hw_initialization_data.md">VIDEO_HW_INITIALIZATION_DATA</a>



<a href="..\video\nf-video-videoportverifyaccessranges.md">VideoPortVerifyAccessRanges</a>



<a href="..\video\nf-video-videoportgetaccessranges.md">VideoPortGetAccessRanges</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556159">DriverEntry of Video Miniport Driver</a>



<a href="..\video\nc-video-pminiport_get_registry_routine.md">HwVidQueryNamedValueCallback</a>



<a href="..\video\nf-video-videoportgetbusdata.md">VideoPortGetBusData</a>



<a href="..\video\ns-video-_video_port_config_info.md">VIDEO_PORT_CONFIG_INFO</a>



<a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a>



<a href="..\video\nf-video-videoportgetregistryparameters.md">VideoPortGetRegistryParameters</a>



<a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>



<a href="..\video\nf-video-videoportfreedevicebase.md">VideoPortFreeDeviceBase</a>



<a href="..\video\nc-video-pminiport_query_device_routine.md">HwVidQueryDeviceCallback</a>



<a href="..\video\nf-video-videoportgetdevicedata.md">VideoPortGetDeviceData</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PVIDEO_HW_FIND_ADAPTER callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

