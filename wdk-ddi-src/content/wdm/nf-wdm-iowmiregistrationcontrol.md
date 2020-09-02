---
UID: NF:wdm.IoWMIRegistrationControl
title: IoWMIRegistrationControl function (wdm.h)
description: The IoWMIRegistrationControl routine registers or unregisters the caller as a WMI data provider for a specified device object.
old-location: kernel\iowmiregistrationcontrol.htm
tech.root: kernel
ms.assetid: fe135118-1992-43c7-8492-81f9febd79b9
ms.date: 04/30/2018
keywords: ["IoWMIRegistrationControl function"]
ms.keywords: IoWMIRegistrationControl, IoWMIRegistrationControl routine [Kernel-Mode Driver Architecture], k104_69efd10b-fb1a-4d66-939d-6ade4185605d.xml, kernel.iowmiregistrationcontrol, wdm/IoWMIRegistrationControl
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoPassive5, LowerDriverReturn, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoWMIRegistrationControl
 - wdm/IoWMIRegistrationControl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoWMIRegistrationControl
---

# IoWMIRegistrationControl function


## -description

The <b>IoWMIRegistrationControl</b> routine registers or unregisters the caller as a WMI data provider for a specified device object.

## -parameters

### -param DeviceObject 

[in]
A pointer to a device object. This object is a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> system structure.

### -param Action 

[in]
The action that WMI should take. The requested action is indicated by one of the following values.

<table>
<tr>
<th>Action value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WMIREG_ACTION_REGISTER

</td>
<td>
Specifies that WMI should register the caller as a WMI provider for <i>DeviceObject</i>. This will result in WMI sending an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-reginfo">IRP_MN_REGINFO</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-reginfo-ex">IRP_MN_REGINFO_EX</a> request to the driver.

</td>
</tr>
<tr>
<td>
WMIREG_ACTION_DEREGISTER

</td>
<td>
Specifies that WMI should remove the caller from its list of WMI providers for <i>DeviceObject</i>.

</td>
</tr>
<tr>
<td>
WMIREG_ACTION_REREGISTER

</td>
<td>
Specifies that WMI should unregister the driver and then register (reregister) the driver. Reregistering the driver results in WMI sending an <b>IRP_MN_REGINFO</b> or <b>IRP_MN_REGINFO_EX</b> request to the driver.

</td>
</tr>
<tr>
<td>
WMIREG_ACTION_UPDATE_GUIDS

</td>
<td>
Specifies that WMI should re-query the driver for a new list of GUID identifiers that it provides data for. This will result in WMI sending an <b>IRP_MN_REGINFO</b> or <b>IRP_MN_REGINFO_EX</b> request to the driver.

</td>
</tr>
</table>

## -returns

<b>IoWMIRegistrationControl</b> returns a status code from the following list:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
Indicates that WMI completed the action requested without error.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the action, specified in <i>Action</i>, was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_<i>XXX</i></b></dt>
</dl>
</td>
<td width="60%">
Indicates that the request failed for the reason specified by the NTSTATUS value. See Ntstatus.h for detailed information for the actual status return code.

</td>
</tr>
</table>

## -remarks

After a driver calls <b>IoWMIRegistrationControl</b>, WMI sends the driver an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-reginfo">IRP_MN_REGINFO</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-reginfo-ex">IRP_MN_REGINFO_EX</a> request so the driver can provide information to WMI. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/registering-as-a-wmi-data-provider">Registering as a WMI Data Provider</a>.

If the caller specifies WMIREG_ACTION_DEREGISTER for <i>Action</i>, <b>IoWMIRegistrationControl</b> causes the calling thread to block until all <b>IRP_MJ_SYSTEM_CONTROL</b> requests that were previously sent to the specified device object have completed. In such a case, if a driver calls <b>IoWMIRegistrationControl</b> within a dispatch routine for an <b>IRP_MJ_SYSTEM_CONTROL</b> request, the calling thread will deadlock.

If a device is removed suddenly (for example, in a surprise removal), causing the PnP manager to send an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-surprise-removal">IRP_MN_SURPRISE_REMOVAL</a> IRP, the driver must call <b>IoWMIRegistrationControl</b> and specify WMIREG_ACTION_DEREGISTER in <i>Action</i> in the call. Note that if the driver calls <b>IoWMIRegistrationControl</b> with <i>Action</i> set to WMIREG_ACTION_DEREGISTER in response to an <b>IRP_MN_SURPRISE_REMOVAL</b> IRP, the driver must not make the same call to <b>IoWMIRegistrationControl</b> in response to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-remove-device">IRP_MN_REMOVE_DEVICE</a> IRP.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-reginfo">IRP_MN_REGINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-reginfo-ex">IRP_MN_REGINFO_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-remove-device">IRP_MN_REMOVE_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-surprise-removal">IRP_MN_SURPRISE_REMOVAL</a>

