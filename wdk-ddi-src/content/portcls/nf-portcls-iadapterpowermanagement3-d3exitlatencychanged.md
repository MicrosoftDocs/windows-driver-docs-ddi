---
UID: NF:portcls.IAdapterPowerManagement3.D3ExitLatencyChanged
title: IAdapterPowerManagement3::D3ExitLatencyChanged method
author: windows-driver-content
description: PortCls calls the D3ExitLatencyChanged method while the device is in sleep (D3) power state, to provide a new exit latency value.
old-location: audio\iadapterpowermanagement3_d3exitlatencychanged.htm
old-project: audio
ms.assetid: B62920AB-39B2-4A04-AFB9-9C935A273F9A
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IAdapterPowerManagement3, D3ExitLatencyChanged, IAdapterPowerManagement3::D3ExitLatencyChanged, IAdapterPowerManagement3 interface [Audio Devices], D3ExitLatencyChanged method, D3ExitLatencyChanged method [Audio Devices], D3ExitLatencyChanged method [Audio Devices], IAdapterPowerManagement3 interface, portcls/IAdapterPowerManagement3::D3ExitLatencyChanged, audio.iadapterpowermanagement3_d3exitlatencychanged
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	IAdapterPowerManagement3.D3ExitLatencyChanged
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# IAdapterPowerManagement3::D3ExitLatencyChanged method


## -description


PortCls calls the D3ExitLatencyChanged method while the device is in sleep (D3) power state, to provide a new exit latency value.


## -syntax


````
NTSTATUS D3ExitLatencyChanged(
  [in] PC_EXIT_LATENCY NewD3ExitLatency
);
````


## -parameters




### -param NewD3ExitLatency [in]

The  <a href="..\portcls\ne-portcls-_pc_exit_latency.md">PC_EXIT_LATENCY</a> enumerated value that Portcls has determined for the device.


## -returns


This method returns an NTSTATUS value.



## -remarks


 The D3ExitLatencyChanged method is only called when the device is the D3 power state. When Portcls wakes the device into D0, it does so via <a href="https://msdn.microsoft.com/library/windows/hardware/jj200332">PowerChangeState3</a>, and the device must be able to exit its sleep state within the latency period indicated by <i>NewD3ExitLatency</i>. Waking the audio adapter in this manner allows the driver to use the most appropriate method to adjust the power state of the audio adapter within the time-frame indicated  by the <i>NewD3ExitLatency</i> value.

The following table shows the possible values for <i>NewD3ExitLatency</i>.
  <table>
<tr>
<th>Exit Latency</th>
<th>Meaning</th>
</tr>
<tr>
<td>PcExitLatencyInstant </td>
<td>The driver must wake the audio adapter instantly with no latency. </td>
</tr>
<tr>
<td>PcExitLatencyFast </td>
<td>The driver must wake the audio adapter  within 10 milliseconds.</td>
</tr>
<tr>
<td>PcExitLatencyResponsive</td>
<td>The driver must wake the audio adapter  within 200 milliseconds.</td>
</tr>
</table>
 





## -see-also

<a href="..\portcls\nn-portcls-iadapterpowermanagement3.md">IAdapterPowerManagement3</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/jj200332">PowerChangeState3</a>

<a href="..\portcls\ne-portcls-_pc_exit_latency.md">PC_EXIT_LATENCY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IAdapterPowerManagement3::D3ExitLatencyChanged method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

