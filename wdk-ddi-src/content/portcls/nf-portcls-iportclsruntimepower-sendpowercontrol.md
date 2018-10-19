---
UID: NF:portcls.IPortClsRuntimePower.SendPowerControl
title: IPortClsRuntimePower::SendPowerControl
author: windows-driver-content
description: The port class driver (PortCls) uses the SendPowerControl method to send power control codes to the audio adapter.
old-location: audio\iportclsruntimepower_sendpowercontrol.htm
tech.root: audio
ms.assetid: 04B8EE71-59F9-4DE4-AD36-846632D3EBB4
ms.date: 05/08/2018
ms.keywords: IPortClsRuntimePower interface [Audio Devices],SendPowerControl method, IPortClsRuntimePower.SendPowerControl, IPortClsRuntimePower::SendPowerControl, SendPowerControl, SendPowerControl method [Audio Devices], SendPowerControl method [Audio Devices],IPortClsRuntimePower interface, audio.iportclsruntimepower_sendpowercontrol, portcls/IPortClsRuntimePower::SendPowerControl
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
-	IPortClsRuntimePower.SendPowerControl
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortClsRuntimePower::SendPowerControl


## -description


The port class driver (PortCls) uses the <code>SendPowerControl</code>  method to send power control codes to the audio adapter.


## -parameters




### -param _DeviceObject [in]

The device object.


### -param _PowerControlCode [in]

The power control code to be sent to the audio adapter.


### -param _InBuffer [in, optional]

The input buffer.


### -param _InBufferSize [in]

The size of the input buffer.


### -param _OutBuffer [out, optional]

The output buffer.


### -param _OutBufferSize [in]

The size of the output buffer.


### -param _BytesReturned [out, optional]

The number of bytes returned.


## -returns



The <code>SendPowerControl</code> method returns STATUS_SUCCESS, if the call is successful. Otherwise, it returns the appropriate error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265125">IPortClsRuntimePower</a>
 

 

