---
UID: NF:wdfdevice.WDF_DEVICE_POWER_CAPABILITIES_INIT
title: WDF_DEVICE_POWER_CAPABILITIES_INIT function (wdfdevice.h)
description: The WDF_DEVICE_POWER_CAPABILITIES_INIT function initializes a WDF_DEVICE_POWER_CAPABILITIES structure.
old-location: wdf\wdf_device_power_capabilities_init.htm
tech.root: wdf
ms.assetid: 1a4b2708-efe2-47c0-b5b7-4e56f33e0266
ms.date: 02/26/2018
keywords: ["WDF_DEVICE_POWER_CAPABILITIES_INIT function"]
ms.keywords: DFDeviceObjectGeneralRef_888be612-b20f-427f-a098-e6b0f73f8704.xml, WDF_DEVICE_POWER_CAPABILITIES_INIT, WDF_DEVICE_POWER_CAPABILITIES_INIT function, kmdf.wdf_device_power_capabilities_init, wdf.wdf_device_power_capabilities_init, wdfdevice/WDF_DEVICE_POWER_CAPABILITIES_INIT
f1_keywords:
 - "wdfdevice/WDF_DEVICE_POWER_CAPABILITIES_INIT"
 - "WDF_DEVICE_POWER_CAPABILITIES_INIT"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
- wdfdevice.h
api_name:
- WDF_DEVICE_POWER_CAPABILITIES_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_DEVICE_POWER_CAPABILITIES_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_DEVICE_POWER_CAPABILITIES_INIT</b> function initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_capabilities">WDF_DEVICE_POWER_CAPABILITIES</a> structure.


## -parameters




### -param Caps [out]

A pointer to a driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_capabilities">WDF_DEVICE_POWER_CAPABILITIES</a> structure.


## -remarks



The <b>WDF_DEVICE_POWER_CAPABILITIES_INIT</b> function zeros the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_capabilities">WDF_DEVICE_POWER_CAPABILITIES</a> structure and sets the structure's <b>Size</b> member. Then, it does the following:

<ul>
<li>
Sets the <b>DeviceD1</b> and <b>DeviceD2</b> members to <b>WdfUseDefault</b>.

</li>
<li>
Sets the <b>WakeFromD0</b>, <b>WakeFromD1</b>, WakeFromD2, and <b>WakeFromD3</b> members to <b>WdfUseDefault</b>.

</li>
<li>
Sets all device states in the <b>DeviceState</b> array to <b>PowerDeviceMaximum</b>.

</li>
<li>
Sets the <b>DeviceWake</b> and <b>SystemWake</b> members to <b>PowerDeviceMaximum</b>.

</li>
<li>
Sets the <b>D1Latency</b>, <b>D2Latency</b>, and <b>D3Latency</b> members to -1.

</li>
<li>
Sets the <b>IdealDxStateForSx</b> member to <b>PowerDeviceMaximum</b>.

</li>
</ul>
For a code example that uses <b>WDF_DEVICE_POWER_CAPABILITIES_INIT</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicesetpowercapabilities">WdfDeviceSetPowerCapabilities</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_capabilities">WDF_DEVICE_POWER_CAPABILITIES</a>
 

 

