---
UID: NF:wdm.PoRequestPowerIrp
title: PoRequestPowerIrp function (wdm.h)
description: The PoRequestPowerIrp routine allocates a power IRP and sends it to the top driver in the device stack for the specified device.
old-location: kernel\porequestpowerirp.htm
tech.root: kernel
ms.assetid: 99330348-bcc2-4a89-96f8-e1b67d9ebe25
ms.date: 04/30/2018
keywords: ["PoRequestPowerIrp function"]
ms.keywords: PoRequestPowerIrp, PoRequestPowerIrp routine [Kernel-Mode Driver Architecture], kernel.porequestpowerirp, portn_d417d88c-2f6d-4af9-b7de-455dfcc1b9df.xml, wdm/PoRequestPowerIrp
f1_keywords:
 - "wdm/PoRequestPowerIrp"
 - "PoRequestPowerIrp"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: MarkDevicePower, PowerDownFail, PowerUpFail, RequestedPowerIrp, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- PoRequestPowerIrp
product:
- Windows
targetos: Windows
req.typenames: 
---

# PoRequestPowerIrp function


## -description


The <b>PoRequestPowerIrp</b> routine allocates a power <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a> and sends it to the top driver in the device stack for the specified device.


## -parameters




### -param DeviceObject [in]

A pointer to the target <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> for the IRP. In Windows 2000 and later versions of Windows, this parameter can point to a physical device object (<a href="https://docs.microsoft.com/windows-hardware/drivers/">PDO</a>) or a functional device object (<a href="https://docs.microsoft.com/windows-hardware/drivers/">FDO</a>). In Windows 98/Me, this parameter must point to the PDO of the underlying device.


### -param MinorFunction [in]

Specifies one of the following minor power IRP codes: <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-power">IRP_MN_QUERY_POWER</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-set-power">IRP_MN_SET_POWER</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-wait-wake">IRP_MN_WAIT_WAKE</a>.


### -param PowerState [in]

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_power_state">POWER_STATE</a> value to pass in the IRP. For <b>IRP_MN_SET_POWER</b> and <b>IRP_MN_QUERY_POWER</b>, specify the requested new <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/device-power-states">device power state</a>. Possible values are <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/ne-wudfddi-_device_power_state">DEVICE_POWER_STATE</a> values.

For <b>IRP_MN_WAIT_WAKE</b>, specify the lowest (least-powered) <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/system-power-states">system power state</a> from which the device should be allowed to wake the system. Possible values are <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_system_power_state">SYSTEM_POWER_STATE</a> values.


### -param CompletionFunction [in, optional]

A pointer to the caller's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-request_power_complete">PowerCompletion</a> callback routine. The I/O manager calls this routine when the IRP has completed. This parameter is optional and can be set to <b>NULL</b> if no <i>PowerCompletion</i> callback routine is needed.


### -param Context [in, optional]

A pointer to a caller-supplied context to be passed through to the <i>PowerCompletion</i> callback. When the caller requests a device set-power IRP in response to a system set-power IRP, <i>Context</i> should contain the system set-power IRP that triggered the request.


### -param Irp [out]

A pointer to a caller-supplied variable in which <b>PoRequestPowerIrp</b> returns a pointer to the IRP that it allocates. Specify a value for <i>Irp</i> only if the <i>MinorFunction</i> parameter is set to <b>IRP_MN_WAIT_WAKE</b>. Otherwise, this parameter should always be <b>NULL</b> because the IRP might be completed before <b>PoRequestPowerIrp</b> returns, causing this parameter to point to memory that has already been discarded.


## -returns



<b>PoRequestPowerIrp</b> returns one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The IRP has been sent.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The routine could not allocate the IRP.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
<i>MinorFunction</i> does not signify a valid minor power IRP code.

</td>
</tr>
</table>
 




## -remarks



A device power policy owner calls this routine to send a wait/wake, query, or set-power IRP.

A driver calls <b>PoRequestPowerIrp</b>—not <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateirp">IoAllocateIrp</a>—to allocate and send a power IRP that has minor IRP code <b>IRP_MN_SET_POWER</b>, <b>IRP_MN_QUERY_POWER</b>, or <b>IRP_MN_WAIT_WAKE</b>. (A driver must call <b>IoAllocateIrp</b> to send a power IRP with minor IRP code <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-power-sequence">IRP_MN_POWER_SEQUENCE</a>.) 

If <b>PoRequestPowerIrp</b> returns a status value of STATUS_PENDING, the routine successfully allocated a device power IRP and sent it to the top of the device stack for the device. After the bus driver and all other drivers have completed the IRP, and the I/O manager has called all <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_completion_routine">IoCompletion</a> routines set by drivers as they passed the IRP down the device stack, the I/O manager calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-request_power_complete">PowerCompletion</a> routine and passes to this routine the specified <i>Context</i> value. If <b>PoRequestPowerIrp</b> returns a status other than STATUS_PENDING, the routine did not send a device power IRP and the <i>PowerCompletion</i> routine is not called.

The <i>PowerCompletion</i> routine performs any additional tasks the sender of the IRP requires after all other drivers have completed the IRP. It need not free the IRP; the power manager does that. In Windows 2000 and later versions of Windows, the <i>PowerCompletion</i> routine can be called at IRQL = PASSIVE_LEVEL or IRQL = DISPATCH_LEVEL. In Windows 98/Me, the <i>PowerCompletion</i> routine is always called at IRQL = PASSIVE_LEVEL, and drivers must complete IRPs at IRQL = PASSIVE_LEVEL.

A device power policy owner calls <b>PoRequestPowerIrp</b> to send a device query- or set-power IRP when it receives a system query- or set-power IRP. The driver should set an <i>IoCompletion</i> routine in the system IRP and pass the system IRP to the next lower driver. The <i>IoCompletion</i> routine calls <b>PoRequestPowerIrp</b> to send the device IRP, passing the system IRP in the <i>Context</i> parameter. The <i>Context</i> parameter is subsequently passed to the <i>PowerCompletion</i> routine for the device IRP. In the <i>PowerCompletion</i> routine, the driver can complete the system IRP. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/sending-irp-mn-query-power-or-irp-mn-set-power-for-device-power-states">Sending IRP_MN_QUERY_POWER or IRP_MN_SET_POWER for Device Power States</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/wait-wake-callback-routines">Wait/Wake Callback Routines</a>.

Drivers can use the returned <i>Irp</i> to cancel an <b>IRP_MN_WAIT_WAKE</b> IRP. Drivers that are requesting other types of power IRPs must pass <b>NULL</b> for this parameter.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-power-sequence">IRP_MN_POWER_SEQUENCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-power">IRP_MN_QUERY_POWER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-set-power">IRP_MN_SET_POWER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-wait-wake">IRP_MN_WAIT_WAKE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateirp">IoAllocateIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-postartnextpowerirp">PoStartNextPowerIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-request_power_complete">PowerCompletion</a>
 

 

