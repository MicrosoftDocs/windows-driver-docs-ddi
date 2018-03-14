---
UID: NS:video._VIDEO_HW_INITIALIZATION_DATA
title: "_VIDEO_HW_INITIALIZATION_DATA"
author: windows-driver-content
description: The VIDEO_HW_INITIALIZATION_DATA structure specifies the entry points and storage requirements for the miniport driver. This structure is created on the stack and initialized by the miniport driver's DriverEntry function.
old-location: display\video_hw_initialization_data.htm
old-project: display
ms.assetid: 1f6bc444-12d6-4406-891e-87dfca437284
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PVIDEO_HW_INITIALIZATION_DATA, PVIDEO_HW_INITIALIZATION_DATA, PVIDEO_HW_INITIALIZATION_DATA structure pointer [Display Devices], VIDEO_HW_INITIALIZATION_DATA, VIDEO_HW_INITIALIZATION_DATA structure [Display Devices], Video_Structs_1ab4d104-315b-4b04-b9dc-3088437cc6d3.xml, _VIDEO_HW_INITIALIZATION_DATA, display.video_hw_initialization_data, video/PVIDEO_HW_INITIALIZATION_DATA, video/VIDEO_HW_INITIALIZATION_DATA"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	video.h
api_name:
-	VIDEO_HW_INITIALIZATION_DATA
product: Windows
targetos: Windows
req.typenames: VIDEO_HW_INITIALIZATION_DATA, *PVIDEO_HW_INITIALIZATION_DATA
req.product: Windows 10 or later.
---

# _VIDEO_HW_INITIALIZATION_DATA structure


## -description


The VIDEO_HW_INITIALIZATION_DATA structure specifies the entry points and storage requirements for the miniport driver. This structure is created on the stack and initialized by the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> function.


## -syntax


````
typedef struct _VIDEO_HW_INITIALIZATION_DATA {
  ULONG                          HwInitDataSize;
  INTERFACE_TYPE                 AdapterInterfaceType;
  PVIDEO_HW_FIND_ADAPTER         HwFindAdapter;
  PVIDEO_HW_INITIALIZE           HwInitialize;
  PVIDEO_HW_INTERRUPT            HwInterrupt;
  PVIDEO_HW_START_IO             HwStartIO;
  ULONG                          HwDeviceExtensionSize;
  ULONG                          StartingDeviceNumber;
  PVIDEO_HW_RESET_HW             HwResetHw;
  PVIDEO_HW_TIMER                HwTimer;
  PVIDEO_HW_START_DMA            HwStartDma;
  PVIDEO_HW_POWER_SET            HwSetPowerState;
  PVIDEO_HW_POWER_GET            HwGetPowerState;
  PVIDEO_HW_GET_CHILD_DESCRIPTOR HwGetVideoChildDescriptor;
  PVIDEO_HW_QUERY_INTERFACE      HwQueryInterface;
  ULONG                          HwChildDeviceExtensionSize;
  PVIDEO_ACCESS_RANGE            HwLegacyResourceList;
  ULONG                          HwLegacyResourceCount;
  PVIDEO_HW_LEGACYRESOURCES      HwGetLegacyResources;
  BOOLEAN                        AllowEarlyEnumeration;
  ULONG                          Reserved;
} VIDEO_HW_INITIALIZATION_DATA, *PVIDEO_HW_INITIALIZATION_DATA;
````


## -struct-fields




### -field HwInitDataSize

Is the size in bytes of this structure. In effect, this indicates the version of VIDEO_HW_INITIALIZATION_DATA being used.


### -field AdapterInterfaceType

Is currently ignored by the video port and should remain zero-initialized.


### -field HwFindAdapter

Pointer to the miniport driver's <a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a> function, which is required for all miniport drivers.


### -field HwInitialize

Pointer to the miniport driver's <a href="..\video\nc-video-pvideo_hw_initialize.md">HwVidInitialize</a> function, which is required for all miniport drivers.


### -field HwInterrupt

Pointer to the miniport driver's <a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a> function, which is required only if the miniport driver's adapter generates interrupts. Otherwise, this pointer must be <b>NULL</b>.


### -field HwStartIO

Pointer to the miniport driver's <a href="..\video\nc-video-pvideo_hw_start_io.md">HwVidStartIO</a> function, which is required for all miniport drivers.


### -field HwDeviceExtensionSize

Specifies the size in bytes of the storage the miniport driver requires for its private, adapter-specific device extension. A miniport driver uses this storage to hold driver-determined per-adapter information, such as the mapped logical address ranges for the adapter registers and whatever context information the driver maintains about its I/O operations.

A pointer to the device extension is passed in every call made to the miniport driver's standard functions except <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a>, <a href="..\video\nc-video-pminiport_synchronize_routine.md">HwVidSynchronizeExecutionCallback</a>, and any <i>SvgaHwIoPortXxx</i> functions. The video port driver allocates the memory for the device extension and initializes it with zeros before it is passed to the miniport driver's <a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a> function.


### -field StartingDeviceNumber

Must be set to zero.


### -field HwResetHw

Pointer to the miniport driver's <a href="..\video\nc-video-pvideo_hw_reset_hw.md">HwVidResetHw</a> function, which is required for any miniport driver of an adapter that does not reset fully on a soft reboot of the machine. Drivers of SVGA adapters that are fully reset to a VGA standard character mode on receipt of an INT10, MODE3-type command usually set this to <b>NULL</b>.


### -field HwTimer

Pointer to a miniport driver's <a href="..\video\nc-video-pvideo_hw_timer.md">HwVidTimer</a> function, which is optional. This pointer can be <b>NULL</b>.


### -field HwStartDma

Reserved for system use.


### -field HwSetPowerState

Pointer to the miniport driver's <a href="..\video\nc-video-pvideo_hw_power_set.md">HwVidSetPowerState</a> function, which is required for all miniport drivers.


### -field HwGetPowerState

Pointer to the miniport driver's <a href="..\video\nc-video-pvideo_hw_power_get.md">HwVidGetPowerState</a> function, which is required for all miniport drivers.


### -field HwGetVideoChildDescriptor

Pointer to the miniport driver's <a href="..\video\nc-video-pvideo_hw_get_child_descriptor.md">HwVidGetVideoChildDescriptor</a> function, which is required for all miniport drivers.


### -field HwQueryInterface

Pointer to the miniport driver's <a href="..\video\nc-video-pvideo_hw_query_interface.md">HwVidQueryInterface</a> function. This can be optionally implemented in a miniport driver that supports external programming interfaces for inter-device communication, such as <a href="https://msdn.microsoft.com/5a140cc0-ecc5-46ff-be3f-3c92f0f67dca">I2C</a> (or I²C) support for MPEG decoders. Otherwise, this member should be set to <b>NULL</b>.


### -field HwChildDeviceExtensionSize

Is the size in bytes of the device extension associated with the display output device. The miniport driver should fill in this member only if the miniport driver needs to manage the monitor configuration data separately from the adapter board configuration.


### -field HwLegacyResourceList

Pointer to an array of <a href="..\video\ns-video-_video_access_range.md">VIDEO_ACCESS_RANGE</a> structures. Each structure describes a device I/O port or memory range for the video adapter that is not listed in PCI configuration space.


### -field HwLegacyResourceCount

Is the number of elements in the array to which <b>HwLegacyResourceList</b> points.


### -field HwGetLegacyResources

Pointer to the miniport driver's <a href="..\video\nc-video-pvideo_hw_legacyresources.md">HwVidLegacyResources</a> function, which enables the driver to specify its legacy resources based on its device and vendor IDs.


### -field AllowEarlyEnumeration

Allows the miniport driver to enumerate its child devices before the adapter is started; that is, the video port driver can call <a href="..\video\nc-video-pvideo_hw_get_child_descriptor.md">HwVidGetVideoChildDescriptor</a> before <a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a> when this member is set to <b>TRUE</b>.


### -field Reserved

Reserved for system use.


## -remarks



A miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> function must initialize this structure with zeros before it sets relevant values in any member.

The video port driver will ignore the <b>HwLegacyResourceCount</b> and <b>HwLegacyResourceList</b> members when <b>HwGetLegacyResources</b> is initialized with a pointer to a <a href="..\video\nc-video-pvideo_hw_legacyresources.md">HwVidLegacyResources</a> implementation.




## -see-also

<a href="..\video\nf-video-videoportzeromemory.md">VideoPortZeroMemory</a>



<a href="..\dispmprt\ns-dispmprt-_emulator_access_entry.md">EMULATOR_ACCESS_ENTRY</a>



<a href="..\video\ns-video-_video_access_range.md">VIDEO_ACCESS_RANGE</a>



<a href="..\video\nc-video-pvideo_hw_legacyresources.md">HwVidLegacyResources</a>



<a href="..\video\ns-video-_video_port_config_info.md">VIDEO_PORT_CONFIG_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VIDEO_HW_INITIALIZATION_DATA structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

