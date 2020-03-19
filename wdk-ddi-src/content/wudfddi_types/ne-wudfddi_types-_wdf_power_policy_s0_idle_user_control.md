---
UID: NE:wudfddi_types._WDF_POWER_POLICY_S0_IDLE_USER_CONTROL
title: _WDF_POWER_POLICY_S0_IDLE_USER_CONTROL (wudfddi_types.h)
description: The WDF_POWER_POLICY_S0_IDLE_USER_CONTROL enumeration identifies whether a user can control a device's behavior when the device is idle and the system is in its working (S0) state.
old-location: wdf\wdf_power_policy_s0_idle_user_control.htm
tech.root: wdf
ms.assetid: ee51c436-2d1c-49d0-ab76-337317eeeeda
ms.date: 02/26/2018
keywords: ["_WDF_POWER_POLICY_S0_IDLE_USER_CONTROL enumeration"]
ms.keywords: DFDeviceObjectGeneralRef_3d85e623-4e88-4e66-a21d-489aebd13ddf.xml, IdleAllowUserControl, IdleDoNotAllowUserControl, IdleUserControlInvalid, WDF_POWER_POLICY_S0_IDLE_USER_CONTROL, WDF_POWER_POLICY_S0_IDLE_USER_CONTROL enumeration, _WDF_POWER_POLICY_S0_IDLE_USER_CONTROL, kmdf.wdf_power_policy_s0_idle_user_control, wdf.wdf_power_policy_s0_idle_user_control, wdfdevice/IdleAllowUserControl, wdfdevice/IdleDoNotAllowUserControl, wdfdevice/IdleUserControlInvalid, wdfdevice/WDF_POWER_POLICY_S0_IDLE_USER_CONTROL, wudfddi_types/IdleAllowUserControl, wudfddi_types/IdleDoNotAllowUserControl, wudfddi_types/IdleUserControlInvalid, wudfddi_types/WDF_POWER_POLICY_S0_IDLE_USER_CONTROL
f1_keywords:
 - "wudfddi_types/WDF_POWER_POLICY_S0_IDLE_USER_CONTROL"
req.header: wudfddi_types.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 1.11
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
- wudfddi_types.h
api_name:
- WDF_POWER_POLICY_S0_IDLE_USER_CONTROL
product:
- Windows
targetos: Windows
req.typenames: WDF_POWER_POLICY_S0_IDLE_USER_CONTROL
---

# _WDF_POWER_POLICY_S0_IDLE_USER_CONTROL enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_POWER_POLICY_S0_IDLE_USER_CONTROL</b> enumeration identifies whether a user can control a device's behavior when the device is idle and the system is in its working (S0) state.


## -enum-fields




### -field IdleUserControlInvalid

For internal use only.


### -field IdleDoNotAllowUserControl

Users cannot control the device's idle behavior.


### -field IdleAllowUserControl

Users can control the device's idle behavior.


## -remarks



The <b>WDF_POWER_POLICY_S0_IDLE_USER_CONTROL</b> enumeration is used as a member type in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_policy_idle_settings">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure.

Users control a device's idle behavior by modifying information on a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/user-control-of-device-idle-and-wake-behavior">property sheet</a>. The framework creates the property sheet and Device Manager displays it.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_policy_idle_settings">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a>
 

 

