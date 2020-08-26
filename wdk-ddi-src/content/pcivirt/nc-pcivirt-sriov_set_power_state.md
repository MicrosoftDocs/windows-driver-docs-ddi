---
UID: NC:pcivirt.SRIOV_SET_POWER_STATE
title: SRIOV_SET_POWER_STATE (pcivirt.h)
description: Sets the power state of the specified PCI Express SR-IOV Virtual Function (VF).
old-location: pci\sriov_set_power_state.htm
tech.root: PCI
ms.assetid: d43a21cb-5cee-4e72-8f0c-7aa8b2453507
ms.date: 02/24/2018
keywords: ["SRIOV_SET_POWER_STATE callback"]
ms.keywords: PCI.sriov_set_power_state, SRIOV_SET_POWER_STATE, SRIOV_SET_POWER_STATE callback function [Buses], pcivirt/SRIOV_SET_POWER_STATE
f1_keywords:
 - "pcivirt/SRIOV_SET_POWER_STATE"
 - "SRIOV_SET_POWER_STATE"
req.header: pcivirt.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Pcivirt.h
api_name:
- SRIOV_SET_POWER_STATE
targetos: Windows
req.typenames: PARCLASS_INFORMATION, *PPARCLASS_INFORMATION
---

# SRIOV_SET_POWER_STATE callback


## -description


Sets the power state of the specified PCI Express SR-IOV Virtual Function (VF).


## -prototype


```cpp
NTSTATUS  SRIOV_SET_POWER_STATE(
  _In_ PVOID              Context,
  _In_ USHORT             VfIndex,
  _In_ DEVICE_POWER_STATE PowerState,
  _In_ BOOLEAN            Wake
);
```


## -parameters




### -param Context 
[in]
A pointer to a driver-defined context.




### -param VfIndex 
[in]
A zero-based index of the VF to which this power state set operation applies.


### -param PowerState 
[in]
A <a href="..\wudfddi\ne-wudfddi-_device_power_state.md">DEVICE_POWER_STATE</a>-type value that indicates the <b>Dx</b> power state to set.


### -param Wake 
[in]
A boolean value that indicates whether to arm the device for a wake signal (PME for PCI Express devices), as it goes into the low power state. TRUE  indicates the device is armed; FALSE otherwise. This value must be FALSE if <i>PowerState</i> is <b>PowerDeviceD0</b>.


## -returns



Set to STATUS_SUCCESS if the request is successful. Otherwise, return appropriate a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code to indicate the error condition.




## -remarks



This callback function is implemented by the physical function (PF) driver. The callback is invoked when the system wants to change the power state of a virtual function.

The PF driver registers its implementation by setting the <b>SetVfPowerState</b> member of the SRIOV_DEVICE_INTERFACE_STANDARD, configuring a <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure, and calling <a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>.

Here is an example implementation of this callback function.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
NTSTATUS
Virtualization_SetPowerState (
    __inout              PVOID              Context,
                         USHORT             VfIndex,
                         DEVICE_POWER_STATE PowerState,
                         BOOLEAN            Wake
    )

{
    PDEVICE_CONTEXT         deviceContext;
    WDF_POWER_DEVICE_STATE  wdfPowerState;
    NTSTATUS                status;

    PAGED_CODE();
    status = STATUS_SUCCESS;

    TraceEvents(TRACE_LEVEL_VERBOSE, DBG_INTERFACE,
                        "Virtualization_SetPowerState received with \
                        VFIndex = %d, PowerState = %d, Wake = %d\n",
                        VfIndex, PowerState, Wake);


    deviceContext = (PDEVICE_CONTEXT) Context;

    if (VfIndex >= deviceContext->NumVFs)
    {
        TraceEvents(TRACE_LEVEL_ERROR, DBG_INTERFACE,
                "VfIndex specified: %d was out of bounds. NumVFs: %d\n",
                VfIndex, deviceContext->NumVFs);
        return STATUS_INVALID_PARAMETER;
    }

    switch (PowerState)
    {
    case PowerDeviceD0:
        wdfPowerState = WdfPowerDeviceD0;
        break;
    case PowerDeviceD1:
        wdfPowerState = WdfPowerDeviceD1;
        break;
    case PowerDeviceD2:
        wdfPowerState = WdfPowerDeviceD2;
        break;
    case PowerDeviceD3:
        wdfPowerState = WdfPowerDeviceD3;
        break;
    default:
        return STATUS_INVALID_PARAMETER;
    }

    WdfWaitLockAcquire(deviceContext->PowerStateLock, NULL);
    deviceContext->VfContext[VfIndex].VfPowerDeviceState = wdfPowerState;
    deviceContext->VfContext[VfIndex].VfWake = Wake;
    WdfWaitLockRelease(deviceContext->PowerStateLock);

    return status;
}
</pre>
</td>
</tr>
</table></span></div>


