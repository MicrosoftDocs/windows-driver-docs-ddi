---
UID: NF:storport.StorPortPoFxActivateComponent
title: StorPortPoFxActivateComponent function (storport.h)
description: The StorPortPoFxActivateComponent routine increments the activation reference count on the specified component of a storage device.
old-location: storage\storportpofxactivatecomponent.htm
tech.root: storage
ms.assetid: 23872334-F9C3-4EB5-9B26-0BDB239D8F4E
ms.date: 03/29/2018
ms.keywords: StorPortPoFxActivateComponent, StorPortPoFxActivateComponent routine [Storage Devices], storage.storportpofxactivatecomponent, storport/StorPortPoFxActivateComponent
f1_keywords:
 - "storport/StorPortPoFxActivateComponent"
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
req.irql: IRQL <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- storport.lib
- storport.dll
api_name:
- StorPortPoFxActivateComponent
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortPoFxActivateComponent function


## -description


The <b>StorPortPoFxActivateComponent</b> routine increments the activation reference count on the specified component of a storage device.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Address [in, optional]

The address of a storage device unit. This parameter is <b>NULL</b> when activating a storage adapter component.


### -param Srb [in, optional]

The SRB triggering the component activation. This parameter is <b>NULL</b> if the miniport is activating a device component for a request not sent through Storport.


### -param Component [in]

The index that identifies the component. This parameter is an index into the <b>Components</b> array in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_stor_pofx_device">STOR_POFX_DEVICE</a> structure that the miniport driver registered for the device with a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinitializepofxpower">StorPortInitializePoFxPower</a>. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


### -param Flags [in]

Not used. Set to 0.


## -returns



The <b>StorPortPoFxActivateComponent</b> routine returns one of these status codes:

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
The storage device activation reference was successfully incremented and the component is in the active state.

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

The storage device is  not registered with the power management framework (PoFx).

-or-

The SRB pointed to by <i>Srb</i> is not sent from Storport.

-or-

The <i>Flags</i> parameter is nonzero.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
TThe adapter or unit does not support PoFx.

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
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_BUSY</b></dt>
</dl>
</td>
<td width="60%">
 The storage device activation reference was successfully incremented but the component is still in the idle state

</td>
</tr>
</table>
 




## -remarks



Currently, both adapter devices and unit devices have maximum component count of 1. The index in <i>Component</i> must always be set to 0.

Each call to <b>StorPortPoFxActivateComponent</b> must be matched with a subsequent call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportpofxidlecomponent">StorPortPoFxIdleComponent</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_stor_pofx_device">STOR_POFX_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinitializepofxpower">StorPortInitializePoFxPower</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportpofxidlecomponent">StorPortPoFxIdleComponent</a>
 

 

