---
UID: NF:wdfdevice.WDF_DEVICE_POWER_CAPABILITIES_INIT
title: WDF_DEVICE_POWER_CAPABILITIES_INIT function
author: windows-driver-content
description: The WDF_DEVICE_POWER_CAPABILITIES_INIT function initializes a WDF_DEVICE_POWER_CAPABILITIES structure.
old-location: wdf\wdf_device_power_capabilities_init.htm
old-project: wdf
ms.assetid: 1a4b2708-efe2-47c0-b5b7-4e56f33e0266
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_DEVICE_POWER_CAPABILITIES_INIT, kmdf.wdf_device_power_capabilities_init, wdfdevice/WDF_DEVICE_POWER_CAPABILITIES_INIT, wdf.wdf_device_power_capabilities_init, DFDeviceObjectGeneralRef_888be612-b20f-427f-a098-e6b0f73f8704.xml, WDF_DEVICE_POWER_CAPABILITIES_INIT function
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfdevice.h
apiname:
-	WDF_DEVICE_POWER_CAPABILITIES_INIT
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WDF_DEVICE_POWER_CAPABILITIES_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_DEVICE_POWER_CAPABILITIES_INIT</b> function initializes a <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_capabilities.md">WDF_DEVICE_POWER_CAPABILITIES</a> structure.


## -syntax


````
VOID WDF_DEVICE_POWER_CAPABILITIES_INIT(
  _Out_ PWDF_DEVICE_POWER_CAPABILITIES Caps
);
````


## -parameters




### -param Caps [out]

A pointer to a driver-supplied <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_capabilities.md">WDF_DEVICE_POWER_CAPABILITIES</a> structure.


## -returns


None



## -remarks


The <b>WDF_DEVICE_POWER_CAPABILITIES_INIT</b> function zeros the <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_capabilities.md">WDF_DEVICE_POWER_CAPABILITIES</a> structure and sets the structure's <b>Size</b> member. Then, it does the following:
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
</ul>For a code example that uses <b>WDF_DEVICE_POWER_CAPABILITIES_INIT</b>, see <a href="..\wdfdevice\nf-wdfdevice-wdfdevicesetpowercapabilities.md">WdfDeviceSetPowerCapabilities</a>.



## -see-also

<a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_capabilities.md">WDF_DEVICE_POWER_CAPABILITIES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DEVICE_POWER_CAPABILITIES_INIT function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

