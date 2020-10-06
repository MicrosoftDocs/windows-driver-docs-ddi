---
UID: NF:storport.StorPortPoFxSetComponentLatency
title: StorPortPoFxSetComponentLatency function (storport.h)
description: The StorPortPoFxSetComponentLatency routine specifies the maximum latency that can be tolerated in the transition from the idle condition to the active condition in the specified storage device component.
old-location: storage\storportpofxsetcomponentlatency.htm
tech.root: storage
ms.assetid: F175ED42-3DB6-4568-96CA-EFC283B14887
ms.date: 03/29/2018
keywords: ["StorPortPoFxSetComponentLatency function"]
ms.keywords: StorPortPoFxSetComponentLatency, StorPortPoFxSetComponentLatency routine [Storage Devices], storage.storportpofxsetcomponentlatency, storport/StorPortPoFxSetComponentLatency
req.header: storport.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in starting with Windows 8.
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
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortPoFxSetComponentLatency
 - storport/StorPortPoFxSetComponentLatency
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortPoFxSetComponentLatency
---

# StorPortPoFxSetComponentLatency function


## -description

The <b>StorPortPoFxSetComponentLatency</b> routine specifies the maximum latency that can be tolerated in the transition from the idle condition to the active condition in the specified storage device component.

## -parameters

### -param HwDeviceExtension 

[in]
A pointer to the hardware device extension for the host bus adapter (HBA). This is the device extension used to register the device in a prior call to <a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportinitializepofxpower">StorPortInitializePoFxPower</a>.

### -param Address 

[in, optional]
The address of a storage device unit. This parameter is <b>NULL</b> when setting the latency of a storage adapter component.

### -param Component 

[in]
The index that identifies the component. This parameter is an index into the <b>Components</b> array in the <a href="/windows-hardware/drivers/ddi/storport/ns-storport-_stor_pofx_device">STOR_POFX_DEVICE</a> structure that the miniport driver registered for the device with a call to <a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportinitializepofxpower">StorPortInitializePoFxPower</a>. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.

### -param Latency 

[in]
The time, in units of 100 nanoseconds, that the storage device component can tolerate  for a transition from an  idle state the active state.

## -returns

The <b>StorPortPoFxSetComponentLatency</b> routine returns one of these status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The component latency successfully set.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Either <i>HwDeviceExtension</i> or <i>Device</i> is NULL.

-or-

<i>Address</i> points to an invalid unit address structure.

-or-

The storage device specified by <i>Address</i> is not found.

-or-

The index in <i>Component</i> specifies a component greater than the component count for the device.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The storage device is  not registered with the  power management framework (PoFx).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_IRQL</b></dt>
</dl>
</td>
<td width="60%">
The current IRQL > DISPATCH_LEVEL.

</td>
</tr>
</table>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxsetcomponentlatency">PoFxSetComponentLatency</a>