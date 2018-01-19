---
UID: NF:wdfdevice.WDF_POWER_FRAMEWORK_SETTINGS_INIT
title: WDF_POWER_FRAMEWORK_SETTINGS_INIT function
author: windows-driver-content
description: The WDF_POWER_FRAMEWORK_SETTINGS_INIT function initializes a WDF_POWER_FRAMEWORK_SETTINGS structure.
old-location: wdf\wdf_power_framework_settings_init.htm
old-project: wdf
ms.assetid: 26F872A2-7727-4346-BA80-779D082EAE9D
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_POWER_FRAMEWORK_SETTINGS_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 
req.alt-api: WDF_POWER_FRAMEWORK_SETTINGS_INIT
req.alt-loc: wdfdevice.h
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
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WDF_POWER_FRAMEWORK_SETTINGS_INIT function



## -description
<p class="CCE_Message">[Applies to KMDF only]


    The 
  <b>WDF_POWER_FRAMEWORK_SETTINGS_INIT</b> function initializes a <a href="..\wdfdevice\ns-wdfdevice-_wdf_power_framework_settings.md">WDF_POWER_FRAMEWORK_SETTINGS</a> structure.



## -syntax

````
void WDF_POWER_FRAMEWORK_SETTINGS_INIT(
  _Out_ PWDF_POWER_FRAMEWORK_SETTINGS PowerFrameworkSettings
);
````


## -parameters

### -param PowerFrameworkSettings [out]

A pointer to a driver-allocated <a href="..\wdfdevice\ns-wdfdevice-_wdf_power_framework_settings.md">WDF_POWER_FRAMEWORK_SETTINGS</a> structure.


## -returns
This function does not return a value.


## -remarks
The <b>WDF_POWER_FRAMEWORK_SETTINGS_INIT</b> function zeros the specified <a href="..\wdfdevice\ns-wdfdevice-_wdf_power_framework_settings.md">WDF_POWER_FRAMEWORK_SETTINGS</a> structure and sets the structure's <b>Size</b> member.

For a code example that uses <b>WDF_POWER_FRAMEWORK_SETTINGS_INIT</b>, see <a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmassignpowerframeworksettings.md">WdfDeviceWdmAssignPowerFrameworkSettings</a>.


## -see-also
<dl>
<dt>
<a href="..\wdfdevice\ns-wdfdevice-_wdf_power_framework_settings.md">WDF_POWER_FRAMEWORK_SETTINGS</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmassignpowerframeworksettings.md">WdfDeviceWdmAssignPowerFrameworkSettings</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_POWER_FRAMEWORK_SETTINGS_INIT function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

