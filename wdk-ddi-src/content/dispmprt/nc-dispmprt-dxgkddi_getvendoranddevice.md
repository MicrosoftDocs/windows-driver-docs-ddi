---
UID: NC:dispmprt.DXGKDDI_GETVENDORANDDEVICE
title: DXGKDDI_GETVENDORANDDEVICE
description: This routine supplies the Vendor and Device IDs for a PCI Express SR-IOV Virtual Function (VF) to be used as the basis for the more generic Plug and Play IDs for the VF.
tech.root: display
ms.assetid: 52b16e83-c445-4854-9ef0-2a3f0f6c7c09
ms.date: 04/04/2019
keywords: ["DXGKDDI_GETVENDORANDDEVICE callback function"]
req.header: dispmprt.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - DXGKDDI_GETVENDORANDDEVICE
 - dispmprt/DXGKDDI_GETVENDORANDDEVICE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_GETVENDORANDDEVICE
product:
 - Windows
dev_langs:
 - c++
---

# DXGKDDI_GETVENDORANDDEVICE callback function


## -description

This routine supplies the Vendor and Device IDs for a PCI Express SR-IOV Virtual Function (VF) to be used as the basis for the more generic Plug and Play IDs for the VF. These can’t be read directly from the VF’s configuration space.

## -parameters

### -param Context

[in] The miniport context that is returned by the driver in the [DXGKDDI_SRIOV_INTERFACE](ns-dispmprt-_dxgkddi_sriov_interface.md) structure.

### -param pArgs 

[in, out] A pointer to the DXGKARG_GETVENDORANDDEVICE structure.

## -prototype

```
//Declaration

DXGKDDI_GETVENDORANDDEVICE DxgkddiGetvendoranddevice; 

// Definition

VOID DxgkddiGetvendoranddevice 
(
	HANDLE Context
	DXGKARG_GETVENDORANDDEVICE * pArgs
)
{...}

```

## -remarks

## -see-also

