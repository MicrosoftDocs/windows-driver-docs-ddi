---
UID: NF:portcls.IPortClsRuntimePower.RegisterPowerControlCallback
title: IPortClsRuntimePower::RegisterPowerControlCallback (portcls.h)
description: The port class driver (PortCls) uses the RegisterPowerControlCallback method to register a power control callback.
old-location: audio\iportclsruntimepower_registerpowercontrolcallback.htm
tech.root: audio
ms.assetid: 1500E2C2-240F-4087-9275-9FD4170B8BED
ms.date: 05/08/2018
ms.keywords: IPortClsRuntimePower interface [Audio Devices],RegisterPowerControlCallback method, IPortClsRuntimePower.RegisterPowerControlCallback, IPortClsRuntimePower::RegisterPowerControlCallback, RegisterPowerControlCallback, RegisterPowerControlCallback method [Audio Devices], RegisterPowerControlCallback method [Audio Devices],IPortClsRuntimePower interface, audio.iportclsruntimepower_registerpowercontrolcallback, portcls/IPortClsRuntimePower::RegisterPowerControlCallback
ms.topic: method
f1_keywords:
 - "portcls/IPortClsRuntimePower.RegisterPowerControlCallback"
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
- IPortClsRuntimePower.RegisterPowerControlCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortClsRuntimePower::RegisterPowerControlCallback


## -description


The port class driver (PortCls) uses the <code>RegisterPowerControlCallback</code>  method to register a power control callback.


## -parameters




### -param _DeviceObject [in]

The device object.


### -param _Callback [in]

The callback object.


### -param _Context [in, optional]

The callback context.


## -returns



The <code>RegisterPowerControlCallback</code> method returns STATUS_SUCCESS, if the call is successful. Otherwise, it returns the appropriate error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iportclsruntimepower">IPortClsRuntimePower</a>
 

 

