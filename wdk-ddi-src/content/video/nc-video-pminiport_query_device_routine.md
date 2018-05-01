---
UID: NC:video.PMINIPORT_QUERY_DEVICE_ROUTINE
title: PMINIPORT_QUERY_DEVICE_ROUTINE
author: windows-driver-content
description: HwVidQueryDeviceCallback uses the specified configuration data to configure its adapter, and, possibly, to fill in missing configuration information in the VIDEO_PORT_CONFIG_INFO structure.
old-location: display\hwvidquerydevicecallback.htm
old-project: display
ms.assetid: 81c3f484-427e-43b8-b7dd-12017533560b
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: HwVidQueryDeviceCallback, HwVidQueryDeviceCallback callback function [Display Devices], PMINIPORT_QUERY_DEVICE_ROUTINE, PMINIPORT_QUERY_DEVICE_ROUTINE callback, VideoMiniport_Functions_9da236b0-f97f-410d-a0e7-c65499d7db8b.xml, display.hwvidquerydevicecallback, video/HwVidQueryDeviceCallback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	video.h
api_name:
-	HwVidQueryDeviceCallback
product: Windows
targetos: Windows
req.typenames: 
---

# PMINIPORT_QUERY_DEVICE_ROUTINE callback function


## -description


<i>HwVidQueryDeviceCallback</i> uses the specified configuration data to configure its adapter, and, possibly, to fill in missing configuration information in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570531">VIDEO_PORT_CONFIG_INFO</a> structure.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's per-adapter storage area. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543119">Device Extensions</a>.


### -param Context

Pointer to the context value set up by <a href="https://msdn.microsoft.com/8c880eff-4b4c-439e-9239-f2343c1fe084">HwVidFindAdapter</a>. Usually, it points to the VIDEO_PORT_CONFIG_INFO buffer or to an offset in that buffer.


### -param DeviceDataType

Specifies the type of configuration information that was requested, which is one of the following:

<b>VpBusData</b>

<b><b>VpCmosData</b></b>

<b><b>VpControllerData</b></b>

<b><b>VpMachineData</b></b>

<b><b>VpMonitorData</b></b>

Miniport drivers of x86-type video adapters usually specify <b>VpBusData</b>, particularly for adapters on EISA buses. The <b>VpControllerData</b> and <b>VpMonitorData</b> values have meaning only on ARC-compliant platforms. The <b>VpCmosData</b> and <b>VpMachineData</b> values are seldom used.  


### -param Identifier

Pointer to the name of the device as determined by the ARC firmware. This parameter should be used only on ARC-compliant platforms. Otherwise, this pointer should be <b>NULL</b>.


### -param IdentiferLength


### -param ConfigurationData

Pointer to hardware configuration data. The format of this data is determined by the specified <i>DeviceDataType</i> and by the <b>AdapterInterfaceType</b> value in the VIDEO_PORT_CONFIG_INFO.


### -param ConfigurationDataLength

Specifies the size in bytes of the <i>ConfigurationData</i> buffer. In effect, this indicates how much information was collected from the registry and stored in the <i>ConfigurationData</i> buffer allocated by <a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>.


### -param ComponentInformation

Reserved for system use.


### -param ComponentInformationLength

Reserved for system use.


#### - IdentifierLength

Specifies the size in bytes of the buffered <i>Identifier</i> string<i>.</i> The value should be zero if the machine is not ARC-compliant.


## -returns



<i>HwVidQueryDeviceCallback</i> returns the status of the operation.




## -remarks



<i>HwVidQueryDeviceCallback</i> is passed in a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff570311">VideoPortGetDeviceData</a> from the miniport driver's <a href="https://msdn.microsoft.com/8c880eff-4b4c-439e-9239-f2343c1fe084">HwVidFindAdapter</a> function. <b>VideoPortGetDeviceData</b> calls <i>HwVidQueryDeviceCallback</i> after collecting available configuration information under the <b>\Registry\Machine\Hardware\Description</b> node of the registry.

<i>HwVidQueryDeviceCallback</i> examines the <i>ConfigurationData</i>, collected from the registry by <b>VideoPortGetDeviceData</b>. It uses this information to configure its adapter, and, possibly, to fill in missing configuration information in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570531">VIDEO_PORT_CONFIG_INFO</a> structure.

<i>HwVidQueryDeviceCallback</i> cannot pass access range values found in the <i>ConfigurationData</i> to any <b>VideoPortRead</b><i>Xxx</i> or <b>VideoPortWrite</b><i>Xxx</i> directly; such addresses first must be mapped by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>.

If the <i>ConfigurationData</i> buffer has no access range information and the miniport driver's <i>HwVidFindAdapter</i> function has not already called <a href="https://msdn.microsoft.com/library/windows/hardware/ff570306">VideoPortGetBusData</a> (or <a href="https://msdn.microsoft.com/library/windows/hardware/ff570302">VideoPortGetAccessRanges</a>), its <i>HwVidQueryDeviceCallback</i> function can call <b>VideoPortGetBusData</b>. Access range information returned by <b>VideoPortGetBusData</b> also must be passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff570377">VideoPortVerifyAccessRanges</a>.

If <b>VideoPortVerifyAccessRanges</b> returns NO_ERROR, the miniport driver can call <b>VideoPortGetDeviceBase</b> to obtain mapped logical addresses that it can use to communicate with the adapter by calling the <b>VideoPortRead</b><i>Xxx</i> and/or <b>VideoPortWrite</b><i>Xxx</i> functions.

If it cannot get bus-relative access ranges values by calling <b>VideoPortGetDeviceData</b>, <b>VideoPortGetBusData</b>, or <b>VideoPortGetAccessRanges</b>, a miniport driver can use a set of driver-supplied default access-range values to find its adapter. In these circumstances, the miniport driver must call <b>VideoPortVerifyAccessRanges</b> with the miniport driver-supplied access ranges, and, then call <b>VideoPortGetDeviceBase</b> only if <b>VideoPortVerifyAccessRanges</b> returned NO_ERROR. If a call to <b>VideoPortVerifyAccessRanges</b> is unsuccessful, a given bus-relative range is already in use by the driver of another device.

<i>HwVidQueryDeviceCallback</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570302">VideoPortGetAccessRanges</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570306">VideoPortGetBusData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570311">VideoPortGetDeviceData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570377">VideoPortVerifyAccessRanges</a>
 

 

