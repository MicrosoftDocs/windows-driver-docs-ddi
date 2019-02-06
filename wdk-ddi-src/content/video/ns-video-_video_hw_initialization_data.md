---
UID: NS:video._VIDEO_HW_INITIALIZATION_DATA
title: _VIDEO_HW_INITIALIZATION_DATA (video.h)
description: The VIDEO_HW_INITIALIZATION_DATA structure specifies the entry points and storage requirements for the miniport driver. This structure is created on the stack and initialized by the miniport driver's DriverEntry function.
old-location: display\video_hw_initialization_data.htm
tech.root: display
ms.assetid: 1f6bc444-12d6-4406-891e-87dfca437284
ms.date: 05/10/2018
ms.keywords: "*PVIDEO_HW_INITIALIZATION_DATA, PVIDEO_HW_INITIALIZATION_DATA, PVIDEO_HW_INITIALIZATION_DATA structure pointer [Display Devices], VIDEO_HW_INITIALIZATION_DATA, VIDEO_HW_INITIALIZATION_DATA structure [Display Devices], Video_Structs_1ab4d104-315b-4b04-b9dc-3088437cc6d3.xml, _VIDEO_HW_INITIALIZATION_DATA, display.video_hw_initialization_data, video/PVIDEO_HW_INITIALIZATION_DATA, video/VIDEO_HW_INITIALIZATION_DATA"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	video.h
api_name:
-	VIDEO_HW_INITIALIZATION_DATA
product:
- Windows
targetos: Windows
req.typenames: VIDEO_HW_INITIALIZATION_DATA, *PVIDEO_HW_INITIALIZATION_DATA
---

# _VIDEO_HW_INITIALIZATION_DATA structure


## -description


The VIDEO_HW_INITIALIZATION_DATA structure specifies the entry points and storage requirements for the miniport driver. This structure is created on the stack and initialized by the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> function.


## -struct-fields




### -field HwInitDataSize

Is the size in bytes of this structure. In effect, this indicates the version of VIDEO_HW_INITIALIZATION_DATA being used.


### -field AdapterInterfaceType

Is currently ignored by the video port and should remain zero-initialized.


### -field HwFindAdapter

Pointer to the miniport driver's <a href="https://msdn.microsoft.com/8c880eff-4b4c-439e-9239-f2343c1fe084">HwVidFindAdapter</a> function, which is required for all miniport drivers.


### -field HwInitialize

Pointer to the miniport driver's <a href="https://msdn.microsoft.com/0e43de21-59e5-4368-8ea2-34fa52e99950">HwVidInitialize</a> function, which is required for all miniport drivers.


### -field HwInterrupt

Pointer to the miniport driver's <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> function, which is required only if the miniport driver's adapter generates interrupts. Otherwise, this pointer must be <b>NULL</b>.


### -field HwStartIO

Pointer to the miniport driver's <a href="https://msdn.microsoft.com/82951291-cf3e-486b-ad0e-f347fefe0370">HwVidStartIO</a> function, which is required for all miniport drivers.


### -field HwDeviceExtensionSize

Specifies the size in bytes of the storage the miniport driver requires for its private, adapter-specific device extension. A miniport driver uses this storage to hold driver-determined per-adapter information, such as the mapped logical address ranges for the adapter registers and whatever context information the driver maintains about its I/O operations.

A pointer to the device extension is passed in every call made to the miniport driver's standard functions except <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a>, <a href="https://msdn.microsoft.com/04e3bac6-c905-4c95-bd1b-e85b46c4296d">HwVidSynchronizeExecutionCallback</a>, and any <i>SvgaHwIoPortXxx</i> functions. The video port driver allocates the memory for the device extension and initializes it with zeros before it is passed to the miniport driver's <a href="https://msdn.microsoft.com/8c880eff-4b4c-439e-9239-f2343c1fe084">HwVidFindAdapter</a> function.


### -field StartingDeviceNumber

Must be set to zero.


### -field HwResetHw

Pointer to the miniport driver's <a href="https://msdn.microsoft.com/dae00663-17bd-461d-9b3f-febff2d9811b">HwVidResetHw</a> function, which is required for any miniport driver of an adapter that does not reset fully on a soft reboot of the machine. Drivers of SVGA adapters that are fully reset to a VGA standard character mode on receipt of an INT10, MODE3-type command usually set this to <b>NULL</b>.


### -field HwTimer

Pointer to a miniport driver's <a href="https://msdn.microsoft.com/bd41bbbf-4ec8-4e6c-8620-d8a9fe0b8bad">HwVidTimer</a> function, which is optional. This pointer can be <b>NULL</b>.


### -field HwStartDma

Reserved for system use.


### -field HwSetPowerState

Pointer to the miniport driver's <a href="https://msdn.microsoft.com/d7800ab6-9d8f-47a7-b919-8b6b0197d163">HwVidSetPowerState</a> function, which is required for all miniport drivers.


### -field HwGetPowerState

Pointer to the miniport driver's <a href="https://msdn.microsoft.com/747cfbfb-2a38-4a0d-b8c6-662d0c3967ba">HwVidGetPowerState</a> function, which is required for all miniport drivers.


### -field HwGetVideoChildDescriptor

Pointer to the miniport driver's <a href="https://msdn.microsoft.com/175030c1-95d9-4a3b-976c-16e04852cb91">HwVidGetVideoChildDescriptor</a> function, which is required for all miniport drivers.


### -field HwQueryInterface

Pointer to the miniport driver's <a href="https://msdn.microsoft.com/f16a7fa3-3471-4ccb-b1b4-982d33f930d3">HwVidQueryInterface</a> function. This can be optionally implemented in a miniport driver that supports external programming interfaces for inter-device communication, such as <a href="https://msdn.microsoft.com/5a140cc0-ecc5-46ff-be3f-3c92f0f67dca">I2C</a> (or I²C) support for MPEG decoders. Otherwise, this member should be set to <b>NULL</b>.


### -field HwChildDeviceExtensionSize

Is the size in bytes of the device extension associated with the display output device. The miniport driver should fill in this member only if the miniport driver needs to manage the monitor configuration data separately from the adapter board configuration.


### -field HwLegacyResourceList

Pointer to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff570498">VIDEO_ACCESS_RANGE</a> structures. Each structure describes a device I/O port or memory range for the video adapter that is not listed in PCI configuration space.


### -field HwLegacyResourceCount

Is the number of elements in the array to which <b>HwLegacyResourceList</b> points.


### -field HwGetLegacyResources

Pointer to the miniport driver's <a href="https://msdn.microsoft.com/015086e9-70b4-4756-9945-c9da17829e90">HwVidLegacyResources</a> function, which enables the driver to specify its legacy resources based on its device and vendor IDs.


### -field AllowEarlyEnumeration

Allows the miniport driver to enumerate its child devices before the adapter is started; that is, the video port driver can call <a href="https://msdn.microsoft.com/175030c1-95d9-4a3b-976c-16e04852cb91">HwVidGetVideoChildDescriptor</a> before <a href="https://msdn.microsoft.com/8c880eff-4b4c-439e-9239-f2343c1fe084">HwVidFindAdapter</a> when this member is set to <b>TRUE</b>.


### -field Reserved

Reserved for system use.


## -remarks



A miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> function must initialize this structure with zeros before it sets relevant values in any member.

The video port driver will ignore the <b>HwLegacyResourceCount</b> and <b>HwLegacyResourceList</b> members when <b>HwGetLegacyResources</b> is initialized with a pointer to a <a href="https://msdn.microsoft.com/015086e9-70b4-4756-9945-c9da17829e90">HwVidLegacyResources</a> implementation.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564131">EMULATOR_ACCESS_ENTRY</a>



<a href="https://msdn.microsoft.com/015086e9-70b4-4756-9945-c9da17829e90">HwVidLegacyResources</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570498">VIDEO_ACCESS_RANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570531">VIDEO_PORT_CONFIG_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570493">VideoPortZeroMemory</a>
 

 

