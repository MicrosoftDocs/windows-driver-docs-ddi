---
UID: NF:wdm.PoFxStartDevicePowerManagement
title: PoFxStartDevicePowerManagement function (wdm.h)
description: The PoFxStartDevicePowerManagement routine completes the registration of a device with the power management framework (PoFx) and starts device power management.
old-location: kernel\pofxstartdevicepowermanagement.htm
tech.root: kernel
ms.assetid: DA034B30-203E-4418-B5BD-1094B3D438FE
ms.date: 04/30/2018
ms.keywords: PoFxStartDevicePowerManagement, PoFxStartDevicePowerManagement routine [Kernel-Mode Driver Architecture], kernel.pofxstartdevicepowermanagement, wdm/PoFxStartDevicePowerManagement
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: Ntoskrnl.lib
req.dll: Ntoskrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Ntoskrnl.exe
api_name:
- PoFxStartDevicePowerManagement
product:
- Windows
targetos: Windows
req.typenames: 
---

# PoFxStartDevicePowerManagement function


## -description


The <b>PoFxStartDevicePowerManagement</b> routine completes the registration of a device with the power management framework (PoFx) and starts device power management.


## -parameters




### -param Handle [in]

A handle that represents the registration of the device with the power management framework (PoFx). The device driver previously received this handle from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439521">PoFxRegisterDevice</a> routine.


## -returns



None.




## -remarks



After a driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439521">PoFxRegisterDevice</a> routine to register a device with PoFx, all components in the device are fully on and in the active condition so that the driver can finish initializing the hardware. To start active power management, the driver must call <b>PoFxStartDevicePowerManagement</b>. By default, this call switches all components to the idle condition.

After <b>PoFxStartDevicePowerManagement</b> switches a component to the idle condition, PoFx might immediately start calling the driver's callback routines, even before <b>PoFxStartDevicePowerManagement</b> returns. PoFx calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh406420">ComponentIdleConditionCallback</a> callback routine to indicate that a component has switched to the idle condition. The driver must not access a component that is in the idle condition. Before the driver can access the component, the driver must call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406650">PoFxActivateComponent</a> and wait for PoFx to call the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh406416">ComponentActiveConditionCallback</a> callback routine. This callback informs the driver that the component is in the active condition and can safely be accessed.

If the driver requires a component to be in the active condition immediately after power management starts, the driver must explicitly activate the component by calling the <b>PoFxActivateComponent</b> routine, and this call must occur after the <b>PoFxRegisterDevice</b> call but before the <b>PoFxStartDevicePowerManagement</b> call.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406416">ComponentActiveConditionCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406420">ComponentIdleConditionCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406650">PoFxActivateComponent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439521">PoFxRegisterDevice</a>
 

 

