---
UID: NF:storport.StorPortPoFxPowerControl
title: StorPortPoFxPowerControl function (storport.h)
description: The StorPortPoFxPowerControl routine sends a power control request to the power management framework (PoFx) to forward to the power engine plug-in (PEP).
old-location: storage\storportpofxpowercontrol.htm
tech.root: storage
ms.assetid: 1EBEBD5D-E0E5-48A3-8CDA-C336575E53C6
ms.date: 03/29/2018
ms.keywords: StorPortPoFxPowerControl, StorPortPoFxPowerControl routine [Storage Devices], storage.storportpofxpowercontrol, storport/StorPortPoFxPowerControl
ms.topic: function
f1_keywords:
 - "storport/StorPortPoFxPowerControl"
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
- StorPortPoFxPowerControl
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortPoFxPowerControl function


## -description


The <b>StorPortPoFxPowerControl</b> routine sends a power control request to the power management framework (PoFx) to forward to the power engine plug-in (PEP).


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA). This is the device extension used to register the device in a prior call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinitializepofxpower">StorPortInitializePoFxPower</a>.


### -param Address

<p>A pointer to the power control code. This code is a GUID value that specifies the requested operation.</p>


### -param PowerControlCode [in]

A pointer to the power control code. This code is a GUID value that specifies the requested operation.


### -param InBuffer [in, optional]

A pointer to a caller-allocated buffer that contains the input data for the operation. The format for the data in this buffer depends on the power control code specified by the <i>PowerControlCode</i> parameter. The <i>InBuffer</i> parameter is optional and can be specified as NULL if the specified operation requires no input data.


### -param InBufferSize [in]

The size, in bytes, of the input buffer that is pointed to by the <i>InBuffer</i> parameter. If <i>InBuffer</i> is NULL, set <i>InBufferSize</i> to zero.


### -param OutBuffer [out, optional]

A pointer to a caller-allocated buffer that is to contain the output data from the operation. The format for the data in this buffer depends on the power control code specified by the <i>PowerControlCode</i> parameter. The <i>OutBuffer</i> parameter is optional and can be specified as NULL if the specified operation produces no output data.


### -param OutBufferSize [in]

The size, in bytes, of the output buffer that is pointed to by the <i>OutBuffer</i> parameter. If <i>OutBuffer</i> is NULL, set <i>OutBufferSize</i> to zero.


### -param BytesReturned [out, optional]

A pointer to a location into which the routine writes the number of bytes of data that were written to the buffer that is pointed to by <i>OutBuffer</i>. The number of bytes written will be less than or equal to <i>OutBufferSize</i>. This parameter is optional and can be specified as <b>NULL</b> if the caller does not need to know how many bytes were written to the output buffer.


## -returns



The <b>StorPortPoFxPowerControl</b> routine returns one of these status codes:

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
The power control operation specified in <i>PowerControlCode</i> was successfully executed.

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
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The power control operation was unsuccessful.

</td>
</tr>
</table>
 




## -remarks



A minport driver calls this routine to send a power control request directly to the PEP. A power control request is similar to an I/O control request (IOCTL). Unlike an IOCTL, however, a power control request is sent directly to PEP and is not observed by other device drivers in the device stack. During a <b>StorPortPoFxPowerControl</b> call, the PEP synchronously performs the requested operation.

Similarly, The PEP can send a power control request directly to the miniport. The miniport driver handles this request in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_adapter_control">HwStorAdapterControl</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_unit_control">HwStorUnitControl</a> routines. The <i>ControlType</i> parameter receives the <b>ScsiAdapterPoFxPowerControl</b> type in the <b>HwStorAdapterControl</b> routine and the <b>ScsiUnitPoFxPowerControl</b> in the <b>HwStorUnitControl</b> routine.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_adapter_control">HwStorAdapterControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_unit_control">HwStorUnitControl</a>
 

 

