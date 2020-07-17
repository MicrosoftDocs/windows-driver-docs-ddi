---
UID: NF:portcls.IAdapterPowerManagement3.D3ExitLatencyChanged
title: IAdapterPowerManagement3::D3ExitLatencyChanged (portcls.h)
description: PortCls calls the D3ExitLatencyChanged method while the device is in sleep (D3) power state, to provide a new exit latency value.
old-location: audio\iadapterpowermanagement3_d3exitlatencychanged.htm
tech.root: audio
ms.assetid: B62920AB-39B2-4A04-AFB9-9C935A273F9A
ms.date: 05/08/2018
keywords: ["IAdapterPowerManagement3::D3ExitLatencyChanged"]
ms.keywords: D3ExitLatencyChanged, D3ExitLatencyChanged method [Audio Devices], D3ExitLatencyChanged method [Audio Devices],IAdapterPowerManagement3 interface, IAdapterPowerManagement3 interface [Audio Devices],D3ExitLatencyChanged method, IAdapterPowerManagement3.D3ExitLatencyChanged, IAdapterPowerManagement3::D3ExitLatencyChanged, audio.iadapterpowermanagement3_d3exitlatencychanged, portcls/IAdapterPowerManagement3::D3ExitLatencyChanged
f1_keywords:
 - "portcls/IAdapterPowerManagement3.D3ExitLatencyChanged"
 - "IAdapterPowerManagement3.D3ExitLatencyChanged"
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
- IAdapterPowerManagement3.D3ExitLatencyChanged
product:
- Windows
targetos: Windows
req.typenames: 
---

# IAdapterPowerManagement3::D3ExitLatencyChanged


## -description


PortCls calls the D3ExitLatencyChanged method while the device is in sleep (D3) power state, to provide a new exit latency value.


## -parameters




### -param NewD3ExitLatency [in]

The  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/ne-portcls-_pc_exit_latency">PC_EXIT_LATENCY</a> enumerated value that Portcls has determined for the device.


## -returns



This method returns an NTSTATUS value.




## -remarks



 The D3ExitLatencyChanged method is only called when the device is the D3 power state. When Portcls wakes the device into D0, it does so via <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/jj200332(v=vs.85)">PowerChangeState3</a>, and the device must be able to exit its sleep state within the latency period indicated by <i>NewD3ExitLatency</i>. Waking the audio adapter in this manner allows the driver to use the most appropriate method to adjust the power state of the audio adapter within the time-frame indicated  by the <i>NewD3ExitLatency</i> value.

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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iadapterpowermanagement3">IAdapterPowerManagement3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/ne-portcls-_pc_exit_latency">PC_EXIT_LATENCY</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/jj200332(v=vs.85)">PowerChangeState3</a>
 

 

