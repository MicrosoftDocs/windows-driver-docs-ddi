---
UID: NE:wdfdevice._WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE
title: "_WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE"
description: The WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE enumeration identifies how the idle timeout for a device is determined.
old-location: wdf\wdf_power_policy_idle_timeout_type.htm
tech.root: wdf
ms.assetid: CFB7E2EA-22D9-4181-B773-BC5691B28CFD
ms.date: 02/26/2018
ms.keywords: "*PWDF_POWER_POLICY_IDLE_TIMEOUT_TYPE, DriverManagedIdleTimeout, PWDF_POWER_POLICY_IDLE_TIMEOUT_TYPE, PWDF_POWER_POLICY_IDLE_TIMEOUT_TYPE enumeration pointer, SystemManagedIdleTimeout, SystemManagedIdleTimeoutWithHint, WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE, WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE enumeration, _WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE, kmdf.wdf_power_policy_idle_timeout_type, wdf.wdf_power_policy_idle_timeout_type, wdfdevice/DriverManagedIdleTimeout, wdfdevice/PWDF_POWER_POLICY_IDLE_TIMEOUT_TYPE, wdfdevice/SystemManagedIdleTimeout, wdfdevice/SystemManagedIdleTimeoutWithHint, wdfdevice/WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE"
ms.topic: enum
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfdevice.h
api_name:
-	WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE
product:
- Windows
targetos: Windows
req.typenames: WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE, *PWDF_POWER_POLICY_IDLE_TIMEOUT_TYPE
---

# _WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>


   The <b>WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE</b> enumeration identifies how the idle timeout for a device is determined.


## -enum-fields




### -field DriverManagedIdleTimeout

The idle timeout value is determined by the <b>IdleTimeout</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551270">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure.


### -field SystemManagedIdleTimeout

Starting in Windows 8, the timeout value is determined by the power framework (PoFx). The value of the <b>IdleTimeout</b> member is not used.

On operating systems earlier than Windows 8, the behavior is same as <b>DriverManagedIdleTimeout</b>.


### -field SystemManagedIdleTimeoutWithHint

Starting in Windows 8, the PoFx uses the value specified in the <b>IdleTimeout</b> member as an input when determining at what point after all the components are idle to transition the device to a low-power (Dx) state. This option enables the driver to delay the transition to a low-power state.

Typically, PoFx waits until the end of the time-out interval to initiate the power transition. However, if PoFx is preparing to enter a low-power system state, PoFx might end the time-out interval early.

The  <b>IdleTimeout</b> value is only advisory. The actual duration after which the PoFx allows the device to enter a low-power state might be greater than or less than the <b>IdleTimeout</b> value.

On operating systems earlier than Windows 8, the behavior is the same as <b>DriverManagedIdleTimeout</b>.




## -remarks



The <b>WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE</b> enumeration is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551270">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551270">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a>
 

 

