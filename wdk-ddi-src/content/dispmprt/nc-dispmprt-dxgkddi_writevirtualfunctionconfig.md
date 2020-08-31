---
UID: NC:dispmprt.DXGKDDI_WRITEVIRTUALFUNCTIONCONFIG
title: DXGKDDI_WRITEVIRTUALFUNCTIONCONFIG
author: windows-driver-content
description: This callback function allows the non-privileged virtual machine to set the contents of a PCI Express SR-IOV Virtual Function’s configuration space values.
tech.root: display
ms.assetid: 5731d68a-c733-4af6-9fe3-35ab0aec25b7
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["DXGKDDI_WRITEVIRTUALFUNCTIONCONFIG callback function"]
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
 - DXGKDDI_WRITEVIRTUALFUNCTIONCONFIG
 - dispmprt/DXGKDDI_WRITEVIRTUALFUNCTIONCONFIG
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_WRITEVIRTUALFUNCTIONCONFIG
product:
 - Windows
dev_langs:
 - c++
---

# DXGKDDI_WRITEVIRTUALFUNCTIONCONFIG callback function


## -description

This callback function allows the non-privileged virtual machine to set the contents of a PCI Express SR-IOV Virtual Function’s configuration space values.

## -parameters

### -param Context

[in] The miniport context that is returned by the driver in the [DXGKDDI_SRIOV_INTERFACE](ns-dispmprt-_dxgkddi_sriov_interface.md) structure.

### -param pArgs

[in, out] A pointer to a DXGKARG_WRITEVIRTUALFUNCTIONCONFIG structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds.

## -prototype

```
//Declaration

DXGKDDI_WRITEVIRTUALFUNCTIONCONFIG DxgkddiWritevirtualfunctionconfig; 

// Definition

NTSTATUS DxgkddiWritevirtualfunctionconfig 
(
	HANDLE Context
	DXGKARG_WRITEVIRTUALFUNCTIONCONFIG * pArgs
)
{...}

```

## -remarks

Granting the guest partition direct access to the config space can be problematic, so this function provides a method of safely accessing the virtual functions config block. 

Note that this should return values and side effects as if written to the virtual device’s config block. Use of this interface may accomplish the write by handling it internally inside the driver supplying the interface or by calling [SetVirtualFunctionData](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-set_virtual_device_data) (from the PCI_VIRTUALIZATION_INTERFACE of the lower level PDO) or some combination of the two.

## -see-also

