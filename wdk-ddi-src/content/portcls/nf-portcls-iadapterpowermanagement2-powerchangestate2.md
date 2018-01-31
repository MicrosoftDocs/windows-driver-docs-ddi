---
UID: NF:portcls.IAdapterPowerManagement2.PowerChangeState2
title: IAdapterPowerManagement2::PowerChangeState2 method
author: windows-driver-content
description: Portcls calls the IAdapterPowerManagement2::PowerChangeState2 method to request a change to the new power state. This request is passed on to the adapter driver.
old-location: audio\iadapterpowermanagement2_powerchangestate2.htm
old-project: audio
ms.assetid: 72068476-5821-4646-88b3-06f3a1917fca
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IAdapterPowerManagement2 interface [Audio Devices], PowerChangeState2 method, portcls/IAdapterPowerManagement2::PowerChangeState2, audio.iadapterpowermanagement2_powerchangestate2, PowerChangeState2, audmp-routines_d145e24a-5ef1-44a3-b51b-9ee2c8a89772.xml, IAdapterPowerManagement2, PowerChangeState2 method [Audio Devices], IAdapterPowerManagement2 interface, IAdapterPowerManagement2::PowerChangeState2, PowerChangeState2 method [Audio Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.lib: portcls.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	portcls.h
apiname:
-	IAdapterPowerManagement2.PowerChangeState2
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# IAdapterPowerManagement2::PowerChangeState2 method


## -description


Portcls calls the <code>IAdapterPowerManagement2::PowerChangeState2</code> method to request a change to the new power state. This request is passed on to the adapter driver.


## -syntax


````
void PowerChangeState2(
  [in] DEVICE_POWER_STATE NewDeviceState,
  [in] SYSTEM_POWER_STATE NewSystemState
);
````


## -parameters




#### - NewDeviceState [in]

Specifies the new power state that Portcls has requested for the device. This parameter is an enumeration of type <a href="..\wudfddi\ne-wudfddi-_device_power_state.md">DEVICE_POWER_STATE</a>.


#### - NewSystemState [in]

Specifies the new power state that Portcls has requested for the system. This parameter is an enumeration of type <a href="..\wdm\ne-wdm-_system_power_state.md">SYSTEM_POWER_STATE</a>.


## -returns


None



## -remarks


A power state indicates the level of power consumption of a device or system. As a result, the level of computing activity is directly affected by the power state of a device or system. 

For more information about system power states, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546941">Handling System Power State Requests</a>. For more information about device power states, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554397">Managing Power for Individual Devices</a>.



## -see-also

<a href="..\wdm\ne-wdm-_system_power_state.md">SYSTEM_POWER_STATE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554397">Managing Power for Individual Devices</a>

<a href="..\portcls\nn-portcls-iadapterpowermanagement2.md">IAdapterPowerManagement2</a>

<a href="..\wudfddi\ne-wudfddi-_device_power_state.md">DEVICE_POWER_STATE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546941">Handling System Power State Requests</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IAdapterPowerManagement2::PowerChangeState2 method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

