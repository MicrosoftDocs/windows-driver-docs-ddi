---
UID: NF:portcls.IPortClsRuntimePower.RegisterPowerControlCallback
title: IPortClsRuntimePower::RegisterPowerControlCallback
author: windows-driver-content
description: The port class driver (PortCls) uses the RegisterPowerControlCallback method to register a power control callback.
old-location: audio\iportclsruntimepower_registerpowercontrolcallback.htm
old-project: audio
ms.assetid: 1500E2C2-240F-4087-9275-9FD4170B8BED
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IPortClsRuntimePower interface [Audio Devices],RegisterPowerControlCallback method, IPortClsRuntimePower.RegisterPowerControlCallback, IPortClsRuntimePower::RegisterPowerControlCallback, RegisterPowerControlCallback, RegisterPowerControlCallback method [Audio Devices], RegisterPowerControlCallback method [Audio Devices],IPortClsRuntimePower interface, audio.iportclsruntimepower_registerpowercontrolcallback, portcls/IPortClsRuntimePower::RegisterPowerControlCallback
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Portcls.h
api_name:
-	IPortClsRuntimePower.RegisterPowerControlCallback
product: Windows
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




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265125">IPortClsRuntimePower</a>
 

 

