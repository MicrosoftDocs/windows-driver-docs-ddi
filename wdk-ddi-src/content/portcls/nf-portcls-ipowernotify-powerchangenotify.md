---
UID: NF:portcls.IPowerNotify.PowerChangeNotify
title: IPowerNotify::PowerChangeNotify
author: windows-driver-content
description: The PowerChangeNotify method notifies the miniport driver of changes in the power state.
old-location: audio\ipowernotify_powerchangenotify.htm
tech.root: audio
ms.assetid: bbc49675-93d1-4ea2-9a3d-b72d76521de7
ms.date: 5/8/2018
ms.keywords: IPowerNotify interface [Audio Devices],PowerChangeNotify method, IPowerNotify.PowerChangeNotify, IPowerNotify::PowerChangeNotify, PowerChangeNotify, PowerChangeNotify method [Audio Devices], PowerChangeNotify method [Audio Devices],IPowerNotify interface, audio.ipowernotify_powerchangenotify, audmp-routines_14b6d53d-cf30-47d1-bace-402fe4e5d7ba.xml, portcls/IPowerNotify::PowerChangeNotify
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IPowerNotify.PowerChangeNotify
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPowerNotify::PowerChangeNotify


## -description


The <code>PowerChangeNotify</code> method notifies the miniport driver of changes in the power state.


## -parameters




### -param PowerState [in]

Specifies the current power state. This parameter is a union of type POWER_STATE. The new power state (<i>PowerState</i>.<b>DeviceState</b>) can be one of the DEVICE_POWER_STATE enumeration values listed in <a href="https://msdn.microsoft.com/library/windows/hardware/ff536488">IAdapterPowerManagement::PowerChangeState</a>.


## -returns



None




## -remarks



The PortCls system driver calls the miniport driver's <code>PowerChangeNotify</code> method to notify it of changes in the power state. The purpose of this call is to give the miniport driver an opportunity to save any hardware-specific context just before powering down or to restore a previously saved context just after powering up.

The miniport driver can write to the hardware registers or on-board memory during the <code>PowerChangeNotify</code> call. If the system is powering down (making a state transition away from PowerDeviceD0), the PortCls system driver calls <code>PowerChangeNotify</code> before it calls <b>IAdapterPowerManagement::PowerChangeState</b> and after it has paused any active audio data streams. This gives the miniport driver an opportunity to save any hardware-specific device context before the device powers down. For example, a WavePci miniport driver might need to save its DMA registers if the power down occurs during a sequence of scatter/gather data transfers. If the system is powering up (making a state transition toward PowerDeviceD0), PortCls calls <code>PowerChangeNotify</code> after it calls <b>PowerChangeState</b> and before it restarts any paused audio data streams. This gives the miniport driver an opportunity to restore a previously saved context after the device has powered up.

The code for this method must reside in paged memory.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536488">IAdapterPowerManagement::PowerChangeState</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536947">IPowerNotify</a>
 

 

