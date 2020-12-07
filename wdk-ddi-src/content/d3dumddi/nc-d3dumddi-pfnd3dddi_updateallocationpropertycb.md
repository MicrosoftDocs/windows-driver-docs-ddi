---
UID: NC:d3dumddi.PFND3DDDI_UPDATEALLOCATIONPROPERTYCB
title: PFND3DDDI_UPDATEALLOCATIONPROPERTYCB (d3dumddi.h)
description: The pfnUpdateAllocationPropertyCb functions updates the property of an allocation without creating a new allocation.
old-location: display\pfnupdateallocationpropertycb.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_UPDATEALLOCATIONPROPERTYCB callback function"]
ms.keywords: PFND3DDDI_UPDATEALLOCATIONPROPERTYCB, PFND3DDDI_UPDATEALLOCATIONPROPERTYCB callback, d3dumddi/pfnUpdateAllocationPropertyCb, display.pfnupdateallocationpropertycb, pfnUpdateAllocationPropertyCb, pfnUpdateAllocationPropertyCb callback function [Display Devices]
req.header: d3dumddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PFND3DDDI_UPDATEALLOCATIONPROPERTYCB
 - d3dumddi/PFND3DDDI_UPDATEALLOCATIONPROPERTYCB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - pfnUpdateAllocationPropertyCb
product:
 - Windows
---

# PFND3DDDI_UPDATEALLOCATIONPROPERTYCB callback function


## -description

The <b>pfnUpdateAllocationPropertyCb</b> functions updates the property of an allocation without creating a new allocation.

## -parameters

### -param hDevice

A handle to the display device associated with the allocation

### -param Arg2

*pUpdateAllocationProperty* [in, out]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-d3dddi_updateallocproperty">D3DDDI_UPDATEALLOCPROPERTY</a> structure that describes how to update the allocation with the desired properties.

## -returns

<b>pfnUpdateAllocationPropertyCb</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The properties were successfully updated. The driver can start using the allocation with its new property immediately. PagingFenceValue is invalid, though the driver shouldn't wait on it.|
|STATUS_PENDING|The request has successfully been queued to VidMm and is being processed. The driver must synchronize against the returned PagingFenceValue before using the allocation with its new property. Note that if the driver request is invalid it may still fail at a later point, in which case the device will be put in error.|
|E_INVALIDARG|Invalid call with bad arguments provided.|
|E_OUTOFMEMORY|Desired supported memory segment is full.|
|E_FAIL|An unknown error has occurred.|
