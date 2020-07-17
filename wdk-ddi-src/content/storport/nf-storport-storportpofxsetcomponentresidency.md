---
UID: NF:storport.StorPortPoFxSetComponentResidency
title: StorPortPoFxSetComponentResidency function (storport.h)
description: The StorPortPoFxSetComponentResidency routine sets the estimated time for how long a storage device component is likely to remain idle after the component enters the idle condition.
old-location: storage\storportpofxsetcomponentresidency.htm
tech.root: storage
ms.assetid: 78DFB17E-5351-419A-9B9B-8CBCD7548910
ms.date: 03/29/2018
keywords: ["StorPortPoFxSetComponentResidency function"]
ms.keywords: StorPortPoFxSetComponentResidency, StorPortPoFxSetComponentResidency routine [Storage Devices], storage.storportpofxsetcomponentresidency, storport/StorPortPoFxSetComponentResidency
f1_keywords:
 - "storport/StorPortPoFxSetComponentResidency"
 - "StorPortPoFxSetComponentResidency"
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
req.lib: Storport.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- storport.lib
- storport.dll
api_name:
- StorPortPoFxSetComponentResidency
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortPoFxSetComponentResidency function


## -description


The <b>StorPortPoFxSetComponentResidency</b> routine sets the estimated time for how long a storage device component is likely to remain idle after the component enters the idle condition.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA). This is the device extension used to register the device in a prior call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinitializepofxpower">StorPortInitializePoFxPower</a>.


### -param Address [in, optional]

The address of a storage device unit. This parameter is <b>NULL</b> when setting the residency of  a storage adapter component.


### -param Component [in]

The index that identifies the component. This parameter is an index into the <b>Components</b> array in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_stor_pofx_device">STOR_POFX_DEVICE</a> structure that the miniport driver registered for the device with a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinitializepofxpower">StorPortInitializePoFxPower</a>. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


### -param Residency [in]

The estimated residency time, in 100-nanosecond units. This parameter is a hint to power management framework (PoFx) about how long the component is likely to remain idle after a transition from the active condition to the idle condition.


## -returns



The <b>StorPortPoFxSetComponentResidency</b> routine returns one of these status codes:

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
The component residency is successfully set.

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
The storage device is  not registered with the PoFx.

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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxsetcomponentresidency">PoFxSetComponentResidency</a>
 

 

