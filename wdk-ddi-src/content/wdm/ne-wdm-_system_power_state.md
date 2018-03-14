---
UID: NE:wdm._SYSTEM_POWER_STATE
title: "_SYSTEM_POWER_STATE"
author: windows-driver-content
description: The SYSTEM_POWER_STATE enumeration type is used to indicate a system power state.
old-location: kernel\system_power_state.htm
old-project: kernel
ms.assetid: aa027f03-7d74-4c0e-8f62-d53f41ae86ae
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PSYSTEM_POWER_STATE, PSYSTEM_POWER_STATE, PSYSTEM_POWER_STATE enumeration pointer [Kernel-Mode Driver Architecture], PowerSystemHibernate, PowerSystemMaximum, PowerSystemShutdown, PowerSystemSleeping1, PowerSystemSleeping2, PowerSystemSleeping3, PowerSystemUnspecified, PowerSystemWorking, SYSTEM_POWER_STATE, SYSTEM_POWER_STATE enumeration [Kernel-Mode Driver Architecture], _SYSTEM_POWER_STATE, kernel.system_power_state, sysenum_32377b1c-a5d3-491b-aebd-ee3d40798f73.xml, wdm/PSYSTEM_POWER_STATE, wdm/PowerSystemHibernate, wdm/PowerSystemMaximum, wdm/PowerSystemShutdown, wdm/PowerSystemSleeping1, wdm/PowerSystemSleeping2, wdm/PowerSystemSleeping3, wdm/PowerSystemUnspecified, wdm/PowerSystemWorking, wdm/SYSTEM_POWER_STATE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Ntpoapi.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	SYSTEM_POWER_STATE
product: Windows
targetos: Windows
req.typenames: SYSTEM_POWER_STATE, *PSYSTEM_POWER_STATE
req.product: Windows 10 or later.
---

# _SYSTEM_POWER_STATE enumeration


## -description


The <b>SYSTEM_POWER_STATE</b> enumeration type is used to indicate a <a href="https://msdn.microsoft.com/bb30bc89-d1f2-4cb3-bcfb-fb76c69dba27">system power state</a>.


## -syntax


````
typedef enum _SYSTEM_POWER_STATE { 
  PowerSystemUnspecified  = 0,
  PowerSystemWorking      = 1,
  PowerSystemSleeping1    = 2,
  PowerSystemSleeping2    = 3,
  PowerSystemSleeping3    = 4,
  PowerSystemHibernate    = 5,
  PowerSystemShutdown     = 6,
  PowerSystemMaximum      = 7
} SYSTEM_POWER_STATE, *PSYSTEM_POWER_STATE;
````


## -enum-fields




### -field PowerSystemUnspecified

Indicates an unspecified system power state. 


### -field PowerSystemWorking

Indicates maximum system power, which corresponds to <a href="https://msdn.microsoft.com/library/windows/hardware/ff564591">system working state S0</a>. 


### -field PowerSystemSleeping1

Indicates a <a href="https://msdn.microsoft.com/2fd883b5-4e89-4ce9-b75a-b821348ac860">system sleeping state</a> less than <b>PowerSystemWorking</b> and greater than <b>PowerSystemSleeping2</b>, which corresponds to system power state S1. 


### -field PowerSystemSleeping2

Indicates a system sleeping state less than <b>PowerSystemSleeping1</b> and greater than <b>PowerSystemSleeping3</b>, which corresponds to system power state S2. 


### -field PowerSystemSleeping3

Indicates a system sleeping state less than <b>PowerSystemSleeping2</b> and greater than <b>PowerSystemHibernate</b>, which corresponds to system power state S3. 


### -field PowerSystemHibernate

Indicates the lowest-powered sleeping state, which corresponds to system power state S4. 


### -field PowerSystemShutdown

Indicates the system is turned off, which corresponds to <a href="https://msdn.microsoft.com/library/windows/hardware/ff564572">system shutdown state S5</a>. 


### -field PowerSystemMaximum

The number of system power state values for this enumeration type that represents actual power states. This value is the number of elements in the <b>DeviceState</b> member of the <a href="..\wdm\ns-wdm-_device_capabilities.md">DEVICE_CAPABILITIES</a> structure for a device. The other system power state values are less than this value.


## -remarks



A power state indicates the level of power consumption—and thus the extent of computing activity—by the system or by a single device. The power manager sets the power state of the system as a whole, where the system power state is indicated by one of the values of the <b>SYSTEM_POWER_STATE</b> enumeration type. Device drivers set the power state of their individual devices, where the device power state is indicated by one of the values of the <a href="..\wudfddi\ne-wudfddi-_device_power_state.md">DEVICE_POWER_STATE</a> enumeration type.

For more information about system power states, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546941">Handling System Power State Requests</a> and for more information about device power states, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554397">Managing Power for Individual Devices</a>.

For more information about power management in general, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff548108">Introduction to Power Management</a>.




## -see-also

<a href="..\wudfddi\ne-wudfddi-_device_power_state.md">DEVICE_POWER_STATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20SYSTEM_POWER_STATE enumeration%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

