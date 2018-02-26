---
UID: NF:ksproxy.IKsPin.KsGetCurrentCommunication
title: IKsPin::KsGetCurrentCommunication method
author: windows-driver-content
description: The KsGetCurrentCommunication method retrieves the current communication direction, interface, and medium of a pin.
old-location: stream\ikspin_ksgetcurrentcommunication.htm
old-project: stream
ms.assetid: 3fca9bf5-5430-4877-846e-e796e54991a2
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., :, C, G, I, IKsPin, IKsPin interface [Streaming Media Devices], KsGetCurrentCommunication method, IKsPin::KsGetCurrentCommunication, K, KsGetCurrentCommunication method [Streaming Media Devices], KsGetCurrentCommunication method [Streaming Media Devices], IKsPin interface, KsGetCurrentCommunication,IKsPin.KsGetCurrentCommunication, P, a, c, e, i, ksproxy/IKsPin::KsGetCurrentCommunication, ksproxy_2619bbb1-bc7d-4a69-99fb-2e35a36c4f02.xml, m, n, o, r, s, stream.ikspin_ksgetcurrentcommunication, t, u"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Desktop
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
req.lib: ksproxy.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	ksproxy.h
apiname:
-	IKsPin.KsGetCurrentCommunication
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# IKsPin::KsGetCurrentCommunication method


## -description


The <b>KsGetCurrentCommunication</b> method retrieves the current communication direction, interface, and medium of a pin. 


## -syntax


````
HRESULT KsGetCurrentCommunication(
  [out, optional] KSPIN_COMMUNICATION *Communication,
  [out, optional] KSPIN_INTERFACE     *Interface,
  [out, optional] KSPIN_MEDIUM        *Medium
);
````


## -parameters




### -param Communication [out, optional]

Pointer to a variable that receives one of the following values from the KSPIN_COMMUNICATION enumerated type describing the current communication direction for a pin: 

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
KSPIN_COMMUNICATION_NONE

</td>
<td>
The pin factory does not create any pin instances.

</td>
</tr>
<tr>
<td>
KSPIN_COMMUNICATION_SINK

</td>
<td>
The pin factory creates instances of IRP sink pins. Such pins can only be connected to IRP source pins.

</td>
</tr>
<tr>
<td>
KSPIN_COMMUNICATION_SOURCE

</td>
<td>
The pin factory creates instances of IRP source pins. Such pins can only be connected to IRP sink pins.

</td>
</tr>
<tr>
<td>
KSPIN_COMMUNICATION_BOTH

</td>
<td>
The pin factory creates instances of pins that are both IRP sinks and IRP sources. 

</td>
</tr>
<tr>
<td>
KSPIN_COMMUNICATION_BRIDGE

</td>
<td>
The pin cannot connect to other pins, but instances may be created on it to receive non-KS I/O requests.

</td>
</tr>
</table>
 


### -param Interface [out, optional]

Pointer to a variable that receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563537">KSPIN_INTERFACE</a> structure that describes the current interface for a pin. 


### -param Medium [out, optional]

Pointer to a variable that receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563538">KSPIN_MEDIUM</a> structure that describes the current medium for a pin. 


## -returns



Returns NOERROR if successful; otherwise, returns an error code.




## -remarks



Source pins send IRPs to sink pins. Do not confuse the communication direction with data flow direction. (See <a href="https://msdn.microsoft.com/library/windows/hardware/ff565197">KSPROPERTY_PIN_DATAFLOW</a>.) A source pin may read or write data, and a sink pin may have data read to it or written from it.

The current communication direction, interface, and medium of a pin are a subset of those available to the pin, and are selected when the pin handle is created.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563537">KSPIN_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563538">KSPIN_MEDIUM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565197">KSPROPERTY_PIN_DATAFLOW</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsPin::KsGetCurrentCommunication method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

