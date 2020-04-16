---
UID: NS:video._VIDEO_PORT_CONFIG_INFO
title: _VIDEO_PORT_CONFIG_INFO (video.h)
description: The VIDEO_PORT_CONFIG_INFO structure contains bus-specific adapter configuration information.
old-location: display\video_port_config_info.htm
tech.root: display
ms.assetid: 5861efcb-1792-406a-820a-38fbfb283c1f
ms.date: 05/10/2018
keywords: ["_VIDEO_PORT_CONFIG_INFO structure"]
ms.keywords: "*PVIDEO_PORT_CONFIG_INFO, PVIDEO_PORT_CONFIG_INFO, PVIDEO_PORT_CONFIG_INFO structure pointer [Display Devices], VIDEO_PORT_CONFIG_INFO, VIDEO_PORT_CONFIG_INFO structure [Display Devices], Video_Structs_5566366c-4ec3-4983-873f-28af2fe51bd6.xml, _VIDEO_PORT_CONFIG_INFO, display.video_port_config_info, video/PVIDEO_PORT_CONFIG_INFO, video/VIDEO_PORT_CONFIG_INFO"
f1_keywords:
 - "video/VIDEO_PORT_CONFIG_INFO"
req.header: video.h
req.include-header: Video.h
req.target-type: Windows
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- video.h
api_name:
- VIDEO_PORT_CONFIG_INFO
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_CONFIG_INFO, *PVIDEO_PORT_CONFIG_INFO
---

# _VIDEO_PORT_CONFIG_INFO structure


## -description


The VIDEO_PORT_CONFIG_INFO structure contains bus-specific adapter configuration information. This structure is used to set up the video hardware and to supply the video port driver with configuration information. The video port driver can then allocate necessary system resources for the miniport driver and its adapter.


## -struct-fields




### -field Length

Is the size in bytes of this structure. The video port driver always initializes the <b>Length</b> member. In effect, its value indicates the version of VIDEO_PORT_CONFIG_INFO being used by the system. Because this structure might grow from one version of the system to the next, a miniport driver should check this member to determine whether it is at least <b>sizeof</b>(VIDEO_PORT_CONFIG_INFO) that the miniport driver uses to configure its adapter.


### -field SystemIoBusNumber

Specifies the system-assigned number of the I/O bus on which the miniport driver's adapter might be connected. The video port driver always initializes this member.


### -field AdapterInterfaceType

Specifies the type of bus interface. The video port driver always sets this member based on the bus on which the PnP manager detected the device.


### -field BusInterruptLevel

This member is irrelevant if the video hardware does not generate interrupts, indicated by setting the <b>HwInterrupt</b> member in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_hw_initialization_data">VIDEO_HW_INITIALIZATION_DATA</a> structure to <b>NULL</b>. Otherwise, it specifies the bus-relative IRQL that corresponds to the interrupt request on <b>Isa</b> or <b>MicroChannel</b> type buses. The preset default value for this member is zero. A miniport driver must supply the correct value if it handles interrupts for a video adapter on an <b>Isa</b> or <b>MicroChannel</b> type bus, or for a video adapter configured for level-sensitive interrupts on an <b>Eisa</b> type bus.

If a miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_find_adapter">HwVidFindAdapter</a> function finds that the video adapter does not generate interrupts or that it cannot determine a valid interrupt vector/level for the adapter, <i>HwVidFindAdapter</i> should set both <b>BusInterruptLevel</b> and <b>BusInterruptVector</b> to zero.


### -field BusInterruptVector

This member is irrelevant if the video hardware does not generate interrupts, indicated by setting the <b>HwInterrupt</b> member in the VIDEO_HW_INITIALIZATION_DATA structure to <b>NULL</b>. Otherwise, it specifies the bus-relative vector used by the video hardware on I/O buses that use interrupt vectors, such as PCI buses. The preset default value for this member is zero.

If a miniport driver's <i>HwVidFindAdapter</i> function finds that the video adapter does not generate interrupts or that it cannot determine a valid interrupt vector/level for the adapter, <i>HwVidFindAdapter</i> should set both <b>BusInterruptVector</b> and <b>BusInterruptLevel</b> to zero.


### -field InterruptMode

Indicates whether the video hardware uses <b>Latched</b> or <b>LevelSensitive</b> interrupts. The video port driver initializes this member if it is relevant, but a miniport driver with an ISR should check that it contains the correct value and reset it if necessary.


### -field NumEmulatorAccessEntries

This member and all subsequent members through <b>HardwareStateSize</b> are irrelevant to miniport drivers that do not declare themselves to be VGA-compatible miniport drivers on x86-based NT-based operating system platforms. For miniport drivers that do not support VGA-compatible SVGA adapters on x86-based machines, this member should be zero. Otherwise, it specifies the number of EMULATOR_ACCESS_RANGE-type elements in the following array.


### -field EmulatorAccessEntries

Pointer to an array of emulator access ranges set up by the VGA-compatible miniport driver. Each emulator access range must be a proper subset of the miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_access_range">VIDEO_ACCESS_RANGE</a>-type array. Each element specifies a range of I/O ports to be hooked out by the V86 emulator and, possibly, monitored by a driver-supplied SvgaHwIoPortXxx function whenever an MS-DOS application, running full screen, attempts to write directly to the video adapter registers. Usually, this array describes all I/O port ranges in the corresponding access ranges array. If the miniport driver defines its array of emulator access entries statically in the driver itself, the port driver initializes this pointer to that array. If <i>NumEmulatorAccessEntries</i> is zero, this member is <b>NULL</b>. 



### -field EmulatorAccessEntriesContext

Specifies a value passed with each call to an <i>SvgaHwIoPortXxx</i> function described in the <b>EmulatorAccessEntries</b> array. Usually, a VGA-compatible miniport driver sets the value of this member to the <b>HwDeviceExtension</b> pointer, or to an offset within the device extension, so the miniport driver can maintain state, such as batched application-issued instructions, in its <i>SvgaHwIoPortXxx</i> functions.


### -field VdmPhysicalVideoMemoryAddress

Specifies the base (mapped) logical address of a range of video memory to be mapped into a VDM's address space for x86 BIOS INT10 support. For miniport drivers that do not support VGA-compatible adapters on x86-based machines, this member should be <b>NULL</b>.


### -field VdmPhysicalVideoMemoryLength

Specifies the size in bytes of the range be mapped into a VDM's address space for x86 BIOS support. For miniport drivers that do not support VGA-compatible adapters on x86-based machines, this member should be zero.


### -field HardwareStateSize

Specifies the minimum size in bytes required to store hardware state information in response to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_save_hardware_state">IOCTL_VIDEO_SAVE_HARDWARE_STATE</a> request, which must be supported only by VGA-compatible miniport drivers on x86-based machines. The initialized value for this member is zero. A VGA-compatible miniport driver must set this member to the number of bytes it requires to hold saved adapter state.


### -field DmaChannel

Reserved for system use.


### -field DmaPort

Reserved for system use.


### -field DmaShareable

Reserved for system use.


### -field InterruptShareable

If the miniport driver's device interrupts, this member should be set to zero if the interrupt cannot be shared with another device, or set to one if the interrupt can be shared. Otherwise, a miniport driver can ignore this member.


### -field Master

Reserved for system use.


### -field DmaWidth

Reserved for system use.


### -field DmaSpeed

Reserved for system use.


### -field bMapBuffers

Reserved for system use.


### -field NeedPhysicalAddresses

Reserved for system use.


### -field DemandMode

Reserved for system use.


### -field MaximumTransferLength

Reserved for system use.


### -field NumberOfPhysicalBreaks

Reserved for system use.


### -field ScatterGather

Reserved for system use.


### -field MaximumScatterGatherChunkSize

Reserved for system use.


### -field VideoPortGetProcAddress

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_port_get_proc_address">VideoPortGetProcAddress</a> callback routine. This member is used to find the address of a video port driver function that the video miniport driver can use without linking to it directly. This enables a driver binary to run on an earlier version of Windows. For details, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/using-videoportgetprocaddress">Using VideoPortGetProcAddress</a>.


### -field DriverRegistryPath

Pointer to the registry path containing the device's service. The display driver can use this information in any way it deems useful.


### -field SystemMemorySize

Indicates to a driver the amount, in bytes, of physical memory in the system.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_find_adapter">HwVidFindAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_save_hardware_state">IOCTL_VIDEO_SAVE_HARDWARE_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_access_range">VIDEO_ACCESS_RANGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_hw_initialization_data">VIDEO_HW_INITIALIZATION_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetaccessranges">VideoPortGetAccessRanges</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicedata">VideoPortGetDeviceData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_port_get_proc_address">VideoPortGetProcAddress</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportverifyaccessranges">VideoPortVerifyAccessRanges</a>
 

 

