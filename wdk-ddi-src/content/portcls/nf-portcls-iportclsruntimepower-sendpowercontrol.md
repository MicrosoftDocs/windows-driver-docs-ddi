---
UID: NF:portcls.IPortClsRuntimePower.SendPowerControl
title: IPortClsRuntimePower::SendPowerControl method
author: windows-driver-content
description: The port class driver (PortCls) uses the SendPowerControl method to send power control codes to the audio adapter.
old-location: audio\iportclsruntimepower_sendpowercontrol.htm
old-project: audio
ms.assetid: 04B8EE71-59F9-4DE4-AD36-846632D3EBB4
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: SendPowerControl method [Audio Devices], IPortClsRuntimePower interface, IPortClsRuntimePower::SendPowerControl, SendPowerControl method [Audio Devices], portcls/IPortClsRuntimePower::SendPowerControl, audio.iportclsruntimepower_sendpowercontrol, SendPowerControl, IPortClsRuntimePower, IPortClsRuntimePower interface [Audio Devices], SendPowerControl method
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
-	IPortClsRuntimePower.SendPowerControl
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPortClsRuntimePower::SendPowerControl method


## -description


The port class driver (PortCls) uses the <code>SendPowerControl</code>  method to send power control codes to the audio adapter.


## -syntax


````
NTSTATUS SendPowerControl(
  [in]            PDEVICE_OBJECT DeviceObject,
  [in]            LPCGUID        PowerControlCode,
  [in, optional]  PVOID          InBuffer,
  [in]            SIZE_T         InBufferSize,
  [out, optional] PVOID          OutBuffer,
  [in]            SIZE_T         OutBufferSize,
  [out, optional] PSIZE_T        BytesReturned
);
````


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

<a href="..\portcls\nn-portcls-iportclsruntimepower.md">IPortClsRuntimePower</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortClsRuntimePower::SendPowerControl method%20 RELEASE:%20(2/21/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

