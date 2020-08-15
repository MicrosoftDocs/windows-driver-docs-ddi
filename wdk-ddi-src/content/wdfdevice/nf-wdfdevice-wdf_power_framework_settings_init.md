---
UID: NF:wdfdevice.WDF_POWER_FRAMEWORK_SETTINGS_INIT
title: WDF_POWER_FRAMEWORK_SETTINGS_INIT function (wdfdevice.h)
description: The WDF_POWER_FRAMEWORK_SETTINGS_INIT function initializes a WDF_POWER_FRAMEWORK_SETTINGS structure.
old-location: wdf\wdf_power_framework_settings_init.htm
tech.root: wdf
ms.assetid: 26F872A2-7727-4346-BA80-779D082EAE9D
ms.date: 02/26/2018
keywords: ["WDF_POWER_FRAMEWORK_SETTINGS_INIT function"]
ms.keywords: WDF_POWER_FRAMEWORK_SETTINGS_INIT, WDF_POWER_FRAMEWORK_SETTINGS_INIT function, kmdf.wdf_power_framework_settings_init, wdf.wdf_power_framework_settings_init, wdfdevice/WDF_POWER_FRAMEWORK_SETTINGS_INIT
f1_keywords:
 - "wdfdevice/WDF_POWER_FRAMEWORK_SETTINGS_INIT"
 - "WDF_POWER_FRAMEWORK_SETTINGS_INIT"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
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
- wdfdevice.h
api_name:
- WDF_POWER_FRAMEWORK_SETTINGS_INIT
targetos: Windows
req.typenames: 
---

# WDF_POWER_FRAMEWORK_SETTINGS_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>


    The 
  <b>WDF_POWER_FRAMEWORK_SETTINGS_INIT</b> function initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_power_framework_settings">WDF_POWER_FRAMEWORK_SETTINGS</a> structure.


## -parameters




### -param PowerFrameworkSettings 
[out]
A pointer to a driver-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_power_framework_settings">WDF_POWER_FRAMEWORK_SETTINGS</a> structure.


## -remarks



The <b>WDF_POWER_FRAMEWORK_SETTINGS_INIT</b> function zeros the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_power_framework_settings">WDF_POWER_FRAMEWORK_SETTINGS</a> structure and sets the structure's <b>Size</b> member.


#### Examples

For a code example that uses <b>WDF_POWER_FRAMEWORK_SETTINGS_INIT</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmassignpowerframeworksettings">WdfDeviceWdmAssignPowerFrameworkSettings</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_power_framework_settings">WDF_POWER_FRAMEWORK_SETTINGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmassignpowerframeworksettings">WdfDeviceWdmAssignPowerFrameworkSettings</a>
 

 

