---
UID: NC:d3dkmddi.DXGKDDI_UPDATEMONITORLINKINFO
title: DXGKDDI_UPDATEMONITORLINKINFO (d3dkmddi.h)
description: Implemented by the client driver to allow capabilities of a monitor which are tied to the link through which it is currently attached, to be queried.
ms.assetid: 5fdf54da-03c7-4eb8-a354-bbbcb1335446
ms.date: 10/19/2018
ms.topic: callback
req.header: d3dkmddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE
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
- d3dkmddi.h
api_name:
- DXGKDDI_UPDATEMONITORLINKINFO
product: 
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5, 19H1
---

# DXGKDDI_UPDATEMONITORLINKINFO callback function

## -description

Implemented by the client driver to allow capabilities of a monitor which are tied to the link through which it is currently attached, to be queried.

## -prototype

```cpp
//Declaration

DXGKDDI_UPDATEMONITORLINKINFO DxgkddiUpdatemonitorlinkinfo;

// Definition

NTSTATUS DxgkddiUpdatemonitorlinkinfo
(
	IN_CONST_HANDLE hAdapter
	INOUT_PDXGKARG_UPDATEMONITORLINKINFO pUpdateMonitorLinkInfoArg
)
{...}

```

## -parameters

### -param hAdapter

Identifies the adapter upon which the display timings should be set.

### -param pUpdateMonitorLinkInfoArg

A pointer to a [DXGKARG_UPDATEMONITORLINKINFO](ns-d3dkmddi-_dxgkarg_updatemonitorlinkinfo.md) structure, for which the driver writes the monitor link capabilities.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values). The driver should always return a success code unless there is an error in the parameters or a failure to process the request.

## -remarks

UpdateMonitorLinkCapabilities will be called after the [RecommendMonitorModes](nc-d3dkmddi-dxgkddi_recommendmonitormodes.md) callback function and before mode enumeration, so that capabilities which are not dependent on the specific display configuration can be queried by the OS without adding extra information into the enumeration. Then, by the time RecommendMonitorModes has completed, the driver has fully comprehended the capabilities of the monitor and can report them to the OS. This does not necessarily imply that all such capabilities are available regardless of the display configuration, but it allows the OS to make defined assumptions.

The DXGKARG_UPDATEMONITORLINKINFO structure also passes usage hints to the driver based on OS configuration of the monitor.

This function is always called at PASSIVE level.



## -see-also
