---
UID: NF:portcls.IPortClsRuntimePower.RegisterPowerControlCallback
title: IPortClsRuntimePower::RegisterPowerControlCallback method
author: windows-driver-content
description: The port class driver (PortCls) uses the RegisterPowerControlCallback method to register a power control callback.
old-location: audio\iportclsruntimepower_registerpowercontrolcallback.htm
old-project: audio
ms.assetid: 1500E2C2-240F-4087-9275-9FD4170B8BED
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: RegisterPowerControlCallback method [Audio Devices], IPortClsRuntimePower interface, IPortClsRuntimePower interface [Audio Devices], RegisterPowerControlCallback method, IPortClsRuntimePower, RegisterPowerControlCallback method [Audio Devices], RegisterPowerControlCallback, portcls/IPortClsRuntimePower::RegisterPowerControlCallback, IPortClsRuntimePower::RegisterPowerControlCallback, audio.iportclsruntimepower_registerpowercontrolcallback
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
req.lib: portcls.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Portcls.h
apiname:
-	IPortClsRuntimePower.RegisterPowerControlCallback
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPortClsRuntimePower::RegisterPowerControlCallback method


## -description


The port class driver (PortCls) uses the <code>RegisterPowerControlCallback</code>  method to register a power control callback.


## -syntax


````
NTSTATUS RegisterPowerControlCallback(
  [in]           PDEVICE_OBJECT                      DeviceObject,
  [in]           PCPFNRUNTIME_POWER_CONTROL_CALLBACK Callback,
  [in, optional] PVOID                               Context
);
````


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

<a href="..\portcls\nn-portcls-iportclsruntimepower.md">IPortClsRuntimePower</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortClsRuntimePower::RegisterPowerControlCallback method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

