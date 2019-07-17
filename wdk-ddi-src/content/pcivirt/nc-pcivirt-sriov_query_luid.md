---
UID: NC:pcivirt.SRIOV_QUERY_LUID
title: SRIOV_QUERY_LUID (pcivirt.h)
description: Gets the local unique identifier of the SR-IOV device.
old-location: pci\sriov_query_luid.htm
tech.root: PCI
ms.assetid: 9bb8e54f-b42a-4f61-a3f5-6972141c8f28
ms.date: 02/24/2018
ms.keywords: "*PSRIOV_QUERY_LUID, *PSRIOV_QUERY_LUID callback function pointer [Buses], PCI.sriov_query_luid, SRIOV_QUERY_LUID, SriovQueryLuid, SriovQueryLuid callback function [Buses], pcivirt/SriovQueryLuid"
ms.topic: callback
f1_keywords:
 - "pcivirt/*PSRIOV_QUERY_LUID"
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
- *PSRIOV_QUERY_LUID
product:
- Windows
targetos: Windows
req.typenames: PARCLASS_INFORMATION, *PPARCLASS_INFORMATION
---

# SRIOV_QUERY_LUID callback


## -description


Gets the local unique identifier of the SR-IOV device.


## -prototype


```cpp
SRIOV_QUERY_LUID SriovQueryLuid;

NTSTATUS SriovQueryLuid(
  _In_  PVOID Context,
  _Out_ PLUID Luid
)
{ ... }

typedef SRIOV_QUERY_LUID *PSRIOV_QUERY_LUID;
```


## -parameters




### -param Context [in]

A pointer to a driver-defined context.




### -param Luid [out]

A pointer to the local unique
identifier of the SR_IOV device implementing the interface.


## -returns




Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.




## -remarks



This callback function is implemented by the physical function (PF) driver. It is invoked  when the system wants to get the identifier of a specific virtual function.

The PF driver registers its implementation by setting the <b>QueryLuid</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pcivirt/ns-pcivirt-_sriov_device_interface_standard">SRIOV_DEVICE_INTERFACE_STANDARD</a>, configuring a <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure, and calling <a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>.

Here is an example implementation of this callback function. The PF driver generates a unique identifier by calling <a href="..\ntddk\nf-ntddk-zwallocatelocallyuniqueid.md">ZwAllocateLocallyUniqueId</a>  and stores it in the device context.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
NTSTATUS
Virtualization_QueryLuid (
    _In_        PVOID             Context,
    _Out_       PLUID             Luid
    )
{
    PDEVICE_CONTEXT deviceContext;

    PAGED_CODE();

    deviceContext = (PDEVICE_CONTEXT)Context;
    *Luid = deviceContext->Luid;

    return STATUS_SUCCESS;
}

</pre>
</td>
</tr>
</table></span></div>


