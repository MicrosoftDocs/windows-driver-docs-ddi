---
UID: NF:portcls.PcUnregisterAdapterPowerManagement
title: PcUnregisterAdapterPowerManagement function
author: windows-driver-content
description: The PcUnregisterAdapterPowerManagement function unregisters the audio adapter's power management interface from the PortCls class driver. The PcUnregisterAdapterPowerManagement function is available in Windows 7 and later versions of Windows.
old-location: audio\pcunregisteradapterpowermanagement.htm
tech.root: audio
ms.assetid: a25ee83f-e267-4966-9be2-ddcbc44b5c15
ms.author: windowsdriverdev
ms.date: 5/8/2018
ms.keywords: PcUnregisterAdapterPowerManagement, PcUnregisterAdapterPowerManagement function [Audio Devices], audio.pcunregisteradapterpowermanagement, audpc-routines_c879c8bb-7466-4683-9a39-2a802f1e6529.xml, portcls/PcUnregisterAdapterPowerManagement
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Portcls.lib
-	Portcls.dll
api_name:
-	PcUnregisterAdapterPowerManagement
product:
- Windows
targetos: Windows
req.typenames: 
---

# PcUnregisterAdapterPowerManagement function


## -description


The <b>PcUnregisterAdapterPowerManagement</b> function unregisters the audio adapter's power management interface from the PortCls class driver. The <b>PcUnregisterAdapterPowerManagement</b> function is available in Windows 7 and later versions of Windows.


## -parameters




### -param pDeviceObject [in]

Specifies a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure that represents the functional device object of the adapter.


## -returns



The <b>PcUnregisterAdapterPowerManagement</b> function returns STATUS_SUCCESS if the function call was successful. Otherwise, it returns the appropriate error code.




## -remarks



The <b>PcUnregisterAdapterPowerManagement</b> function unregisters a driver's power management interface that was registered with PortCls by using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537724">PcRegisterAdapterPowerManagement</a> function. <b>PcUnregisterAdapterPowerManagement</b> helps the system to avoid making a power change request while the adapter driver is being unloaded. This function must only be called if the power management interface for the adapter was previously registered with PortCls.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537724">PcRegisterAdapterPowerManagement</a>
 

 

