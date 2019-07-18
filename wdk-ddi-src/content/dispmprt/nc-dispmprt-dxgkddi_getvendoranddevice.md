---
UID: NC:dispmprt.DXGKDDI_GETVENDORANDDEVICE
title: DXGKDDI_GETVENDORANDDEVICE
author: windows-driver-content
description: This routine supplies the Vendor and Device IDs for a PCI Express SR-IOV Virtual Function (VF) to be used as the basis for the more generic Plug and Play IDs for the VF.
tech.root: display
ms.assetid: 52b16e83-c445-4854-9ef0-2a3f0f6c7c09
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: callback
f1_keywords:
 - "dispmprt/DXGKDDI_GETVENDORANDDEVICE"
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
targetos: Windows
ms.custom: 19H1
---

# DXGKDDI_GETVENDORANDDEVICE callback function

## -description

This routine supplies the Vendor and Device IDs for a PCI Express SR-IOV Virtual Function (VF) to be used as the basis for the more generic Plug and Play IDs for the VF. These can’t be read directly from the VF’s configuration space.

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

## -parameters

### -param Context

[in] The miniport context that is returned by the driver in the [DXGKDDI_SRIOV_INTERFACE](ns-dispmprt-_dxgkddi_sriov_interface.md) structure.

### -param pArgs 

[in, out] A pointer to the DXGKARG_GETVENDORANDDEVICE structure.

## -returns

Returns VOID.

## -remarks




## -see-also
