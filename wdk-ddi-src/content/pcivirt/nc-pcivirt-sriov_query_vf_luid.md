---
UID: NC:pcivirt.SRIOV_QUERY_VF_LUID
title: SRIOV_QUERY_VF_LUID
author: windows-driver-content
description: Gets the local unique identifier of the PCI Express SR-IOV Virtual Function (VF).
old-location: pci\sriov_query_vf_luid.htm
tech.root: PCI
ms.assetid: 17fe6e28-59ce-4678-8268-b49cef09a3db
ms.date: 2/24/2018
ms.keywords: "*PSRIOV_QUERY_VF_LUID, *PSRIOV_QUERY_VF_LUID callback function pointer [Buses], PCI.sriov_query_vf_luid, SRIOV_QUERY_VF_LUID, SriovQueryVfLuid, SriovQueryVfLuid callback function [Buses], pcivirt/SriovQueryVfLuid"
ms.topic: callback
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
req.irql:
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	pcivirt.h
api_name:
-	*PSRIOV_QUERY_VF_LUID
product:
- Windows
targetos: Windows
req.typenames: PARCLASS_INFORMATION, *PPARCLASS_INFORMATION
---

# SRIOV_QUERY_VF_LUID callback


## -description


Gets the local unique identifier of the PCI Express SR-IOV Virtual Function (VF).


## -prototype


```cpp
SRIOV_QUERY_VF_LUID SriovQueryVfLuid;

NTSTATUS SriovQueryVfLuid(
  _In_  PVOID  Context,
  _In_  USHORT VfIndex,
  _Out_ PLUID  Luid
)
{ ... }

typedef SRIOV_QUERY_VF_LUID *PSRIOV_QUERY_VF_LUID;
```


## -parameters




### -param Context [in]

A pointer to a driver-defined context.




### -param VfIndex [in]

A zero-based index of the VF that is being queried.


### -param Luid [out]

A pointer to the local unique
identifier of the SR_IOV device implementing the interface.


## -returns




Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.




## -remarks



This callback function is implemented by the physical function (PF) driver. It is invoked  when the system wants to get the identifier of a specific virtual function.

The PF driver registers its implementation by setting the <b>QueryLuid</b> member of the SRIOV_DEVICE_INTERFACE_STANDARD_2, configuring a <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure, and calling <a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>.

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
    *Luid = deviceContext-&gt;Luid;

    return STATUS_SUCCESS;
}

</pre>
</td>
</tr>
</table></span></div>


