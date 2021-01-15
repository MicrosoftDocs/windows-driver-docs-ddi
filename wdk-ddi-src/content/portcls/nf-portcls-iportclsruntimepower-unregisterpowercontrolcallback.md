---
UID: NF:portcls.IPortClsRuntimePower.UnregisterPowerControlCallback
title: IPortClsRuntimePower::UnregisterPowerControlCallback (portcls.h)
description: The port class driver (PortCls) uses the UnregisterPowerControlCallback method to unregister a power control callback.
old-location: audio\iportclsruntimepower_unregisterpowercontrolcallback.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IPortClsRuntimePower::UnregisterPowerControlCallback"]
ms.keywords: IPortClsRuntimePower interface [Audio Devices],UnregisterPowerControlCallback method, IPortClsRuntimePower.UnregisterPowerControlCallback, IPortClsRuntimePower::UnregisterPowerControlCallback, UnregisterPowerControlCallback, UnregisterPowerControlCallback method [Audio Devices], UnregisterPowerControlCallback method [Audio Devices],IPortClsRuntimePower interface, audio.iportclsruntimepower_unregisterpowercontrolcallback, portcls/IPortClsRuntimePower::UnregisterPowerControlCallback
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPortClsRuntimePower::UnregisterPowerControlCallback
 - portcls/IPortClsRuntimePower::UnregisterPowerControlCallback
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Portcls.h
api_name:
 - IPortClsRuntimePower::UnregisterPowerControlCallback
---

# IPortClsRuntimePower::UnregisterPowerControlCallback


## -description

The port class driver (PortCls) uses the <code>UnregisterPowerControlCallback</code>  method to unregister a power control callback.

## -parameters

### -param _DeviceObject 

[in]
The device object.

## -returns

The <code>UnregisterPowerControlCallback</code> method returns STATUS_SUCCESS, if the call is successful. Otherwise, it returns the appropriate error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iportclsruntimepower">IPortClsRuntimePower</a>

