---
UID: NC:dispmprt.DXGKDDI_COLLECTDIAGNOSTICINFO
title: DXGKDDI_COLLECTDIAGNOSTICINFO
author: windows-driver-content
description: The DxgkDdiCollectDiagnosticInfo callback routine collects the private driver information for reasons that are specified by DXGK_DIAGNOSTICINFO_TYPE.
tech.root: display
ms.assetid: df12fb24-823a-439e-936a-bbf7079cf437
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: callback
req.header: dispmprt.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
 - apiref
api_type: 
 - UserDefined
api_location: 
 - dispmprt.h
api_name: 
 - DXGKDDI_COLLECTDIAGNOSTICINFO
product:
- Windows
targetos: Windows
ms.custom: 19H1
---

# DXGKDDI_COLLECTDIAGNOSTICINFO callback function

## -description

The DxgkDdiCollectDiagnosticInfo callback routine collects the private driver information for reasons that are specified by [DXGK_DIAGNOSTICINFO_TYPE](ne-dispmprt-dxgk_diagnosticinfo_type.md).

In Windows 10, version 1903, the driver will be called to collect private information if the function calls to [DxgkDdiAddDevice](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) or [DxgkDdiStartDevice](../dispmprt/nc-dispmprt-dxgkddi_start_device.md) failed.

## -prototype

```
//Declaration

DXGKDDI_COLLECTDIAGNOSTICINFO DxgkddiCollectdiagnosticinfo; 

// Definition

NTSTATUS DxgkddiCollectdiagnosticinfo 
(
	IN_CONST_PDEVICE_OBJECT PhysicalDeviceObject
	INOUT_PDXGKARG_COLLECTDIAGNOSTICINFO pCollectDiagnosticInfo
)
{...}

```

## -parameters

### -param PhysicalDeviceObject

[in] A pointer to a physical device object (PDO) that identifies a display adapter.

### -param pCollectDiagnosticInfo

[in, out] A pointer to a [DXGKARG_COLLECTDIAGNOSTICINFO](ns-dispmprt-dxgkarg_collectdiagnosticinfo.md) structure which describes information collected by the driver.

## -returns

Return STATUS_SUCCESS if the private data information was successfully collected. Otherwise, returns STATUS_UNSUCCESSFUL if the driver couldn't collect the requested information.

## -remarks

This function is called at PASSIVE level, at any time in between the calls to [DxgkDdiAddDevice](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) and [DxgkDdiStartDevice](../dispmprt/nc-dispmprt-dxgkddi_start_device.md), and should support [synchronization zero level](https://docs.microsoft.com/windows-hardware/drivers/display/threading-and-synchronization-zero-level). The collected data shouldn't contain any private user information.

## -see-also
