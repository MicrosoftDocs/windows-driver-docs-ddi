---
UID: NC:pcivirt.SRIOV_QUERY_PROBED_BARS
title: SRIOV_QUERY_PROBED_BARS (pcivirt.h)
description: Queries the data read from the physical function's (PF) base address registers (BARs) if the value -1 were written to them first.
old-location: pci\sriov_query_probed_bars.htm
tech.root: PCI
ms.assetid: 422a9212-7227-4508-8f06-0056349fa835
ms.date: 02/24/2018
keywords: ["SRIOV_QUERY_PROBED_BARS callback"]
ms.keywords: "*PSRIOV_QUERY_PROBED_BARS, *PSRIOV_QUERY_PROBED_BARS callback function pointer [Buses], PCI.sriov_query_probed_bars, SRIOV_QUERY_PROBED_BARS, SriovQueryProbedBars, SriovQueryProbedBars callback function [Buses], pcivirt/SriovQueryProbedBars"
f1_keywords:
 - "pcivirt/*PSRIOV_QUERY_PROBED_BARS"
 - "*PSRIOV_QUERY_PROBED_BARS"
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
- PSRIOV_QUERY_PROBED_BARS
targetos: Windows
req.typenames: PARCLASS_INFORMATION, *PPARCLASS_INFORMATION
---

# SRIOV_QUERY_PROBED_BARS callback


## -description



Queries the data read from
    the physical  function's (PF) base address registers (BARs) if the value -1 were written to them first.


## -prototype


```cpp
SRIOV_QUERY_PROBED_BARS SriovQueryProbedBars;

NTSTATUS SriovQueryProbedBars(
  _In_  PVOID  Context,
  _Out_ PULONG BaseRegisterValues
)
{ ... }

typedef SRIOV_QUERY_PROBED_BARS *PSRIOV_QUERY_PROBED_BARS;
```


## -parameters




### -param Context [in]

A pointer to a driver-defined context.




### -param BaseRegisterValues [out]

A pointer to an array of variables that is bounded by the number of BARs in a PCI device.


## -returns




Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.




## -remarks



This callback function is implemented by the physical function (PF) driver. It is invoked  when the system wants to get base address register values.

The PF driver registers its implementation by setting the <b>QueryProbedBars</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/ns-pcivirt-_sriov_device_interface_standard">SRIOV_DEVICE_INTERFACE_STANDARD</a>, configuring a <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure, and calling <a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>.



