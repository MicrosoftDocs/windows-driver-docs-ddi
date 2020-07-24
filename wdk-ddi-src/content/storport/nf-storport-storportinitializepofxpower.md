---
UID: NF:storport.StorPortInitializePoFxPower
title: StorPortInitializePoFxPower function (storport.h)
description: A miniport driver calls StorPortInitializePoFxPower to register a storage device with the power management framework (PoFx).
old-location: storage\storportinitializepofxpower.htm
tech.root: storage
ms.assetid: 154EAF9B-4B30-4124-B31D-6C7D09B52674
ms.date: 03/29/2018
keywords: ["StorPortInitializePoFxPower function"]
ms.keywords: StorPortInitializePoFxPower, StorPortInitializePoFxPower routine [Storage Devices], storage.storportinitializepofxpower, storport/StorPortInitializePoFxPower
f1_keywords:
 - "storport/StorPortInitializePoFxPower"
 - "StorPortInitializePoFxPower"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- storport.h
api_name:
- StorPortInitializePoFxPower
targetos: Windows
req.typenames: 
---

# StorPortInitializePoFxPower function


## -description


A miniport driver calls <b>StorPortInitializePoFxPower</b> to register a storage device with the power management framework (PoFx).


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Address [in, optional]

The address of a storage device unit. This parameter is <b>NULL</b> when registering for a storage adapter.


### -param Device [in]

A pointer to a <b>STOR_POFX_DEVICE_V2</b> structure cast to a pointer to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_stor_pofx_device">STOR_POFX_DEVICE</a>. This structure contains a component list with F-states for a storage device.


### -param D3ColdEnabled [in, out]

A pointer to a <b>BOOLEAN</b> value which the Storport driver will set to indicate whether the D3 Cold state is enabled for the storage device.


## -returns



The <b>StorPortInitializePoFxPower</b> routine returns one of these status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
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

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_stor_pofx_device">STOR_POFX_DEVICE</a> structure pointed to by  <i>Device</i> is formatted incorrectly or contains invalid data.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The storage device was successfully registered with PoFx.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Sufficient resources are not available to register the storage device with PoFx.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The storage device was not successfully registered with PoFx.

-or-

The storage device is already registered with PoFx.

</td>
</tr>
</table>
 




## -remarks



Adapter devices are always registered with a <b>NULL</b> value for <i>address</i>. Unit devices are registered by specifying a valid unit address for <i>address</i>.

If the <b>STOR_POFX_DEVICE_FLAG_ENABLE_D3_COLD</b> flag is set in the <b>Flags</b> member of <i>Device</i>, Storport will attempt to enable D3 Cold support for the device component. The D3 Cold enabled status is returned in the <b>BOOLEAN</b> value pointed to by <i>D3ColdEnabled</i>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_stor_pofx_device">STOR_POFX_DEVICE</a>
 

 

