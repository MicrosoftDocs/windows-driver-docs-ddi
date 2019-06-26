---
UID: NF:portcls.IPortClsRuntimePower.UnregisterPowerControlCallback
title: IPortClsRuntimePower::UnregisterPowerControlCallback (portcls.h)
description: The port class driver (PortCls) uses the UnregisterPowerControlCallback method to unregister a power control callback.
old-location: audio\iportclsruntimepower_unregisterpowercontrolcallback.htm
tech.root: audio
ms.assetid: F7E83587-0499-4D56-8D34-5513454FFEE2
ms.date: 05/08/2018
ms.keywords: IPortClsRuntimePower interface [Audio Devices],UnregisterPowerControlCallback method, IPortClsRuntimePower.UnregisterPowerControlCallback, IPortClsRuntimePower::UnregisterPowerControlCallback, UnregisterPowerControlCallback, UnregisterPowerControlCallback method [Audio Devices], UnregisterPowerControlCallback method [Audio Devices],IPortClsRuntimePower interface, audio.iportclsruntimepower_unregisterpowercontrolcallback, portcls/IPortClsRuntimePower::UnregisterPowerControlCallback
ms.topic: method
req.header: portcls.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 7
req.target-min-winversvr: Windows Server 2003
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Portcls.h
api_name:
- IPortClsRuntimePower.UnregisterPowerControlCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortClsRuntimePower::UnregisterPowerControlCallback


## -description


The port class driver (PortCls) uses the <code>UnregisterPowerControlCallback</code>  method to unregister a power control callback.


## -parameters




### -param _DeviceObject [in]

The device object.


## -returns



The <code>UnregisterPowerControlCallback</code> method returns STATUS_SUCCESS, if the call is successful. Otherwise, it returns the appropriate error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iportclsruntimepower">IPortClsRuntimePower</a>
 

 

