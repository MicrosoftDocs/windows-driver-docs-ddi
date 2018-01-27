---
UID: NF:portcls.IPowerNotify.PowerChangeNotify
title: IPowerNotify::PowerChangeNotify method
author: windows-driver-content
description: The PowerChangeNotify method notifies the miniport driver of changes in the power state.
old-location: audio\ipowernotify_powerchangenotify.htm
old-project: audio
ms.assetid: bbc49675-93d1-4ea2-9a3d-b72d76521de7
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PowerChangeNotify method [Audio Devices], IPowerNotify interface, IPowerNotify, IPowerNotify interface [Audio Devices], PowerChangeNotify method, PowerChangeNotify, PowerChangeNotify method [Audio Devices], IPowerNotify::PowerChangeNotify, portcls/IPowerNotify::PowerChangeNotify, audio.ipowernotify_powerchangenotify, audmp-routines_14b6d53d-cf30-47d1-bace-402fe4e5d7ba.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	IPowerNotify.PowerChangeNotify
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPowerNotify::PowerChangeNotify method


## -description


The <code>PowerChangeNotify</code> method notifies the miniport driver of changes in the power state.


## -syntax


````
void PowerChangeNotify(
  [in] POWER_STATE PowerState
);
````


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

<a href="..\portcls\nn-portcls-ipowernotify.md">IPowerNotify</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPowerNotify::PowerChangeNotify method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

