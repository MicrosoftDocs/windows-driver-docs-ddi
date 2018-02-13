---
UID: NF:wdfdevice.WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT
title: WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT function
author: windows-driver-content
description: The WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT function initializes a driver's WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS structure.
old-location: wdf\wdf_device_power_policy_wake_settings_init.htm
old-project: wdf
ms.assetid: bb712c92-c926-4a7a-a126-db4db3bc728f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT, kmdf.wdf_device_power_policy_wake_settings_init, WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT function, DFDeviceObjectGeneralRef_2608d30e-282b-4a19-acb7-ced01cb6bc1a.xml, wdfdevice/WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT, wdf.wdf_device_power_policy_wake_settings_init
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
-	WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT</b> function initializes a driver's <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_policy_wake_settings.md">WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS</a> structure.


## -syntax


````
VOID WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT(
  _Out_ PWDF_DEVICE_POWER_POLICY_WAKE_SETTINGS Settings
);
````


## -parameters




### -param Settings [out]

A pointer to a driver-allocated <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_policy_wake_settings.md">WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS</a> structure.


## -returns



None




## -remarks



The <b>WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT</b> function zeros the specified <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_policy_wake_settings.md">WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS</a> structure and sets the structure's <b>Size</b> member. Then the function sets the structure's <b>Enabled</b> member to <b>WdfUseDefault</b>, sets the <b>DxState</b> member to <b>PowerDeviceMaximum</b>, and sets the <b>UserControlOfWakeSettings</b> member to <b>WakeAllowUserControl</b>.

For a code example that uses <b>WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT</b>, see <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceassignsxwakesettings.md">WdfDeviceAssignSxWakeSettings</a>.



