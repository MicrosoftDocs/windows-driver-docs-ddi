---
UID: NC:d3dumddi.PFND3DDDI_UPDATEALLOCATIONPROPERTYCB
title: PFND3DDDI_UPDATEALLOCATIONPROPERTYCB
author: windows-driver-content
description: The pfnUpdateAllocationPropertyCb functions updates the property of an allocation without creating a new allocation.
old-location: display\pfnupdateallocationpropertycb.htm
old-project: display
ms.assetid: 49E4189A-2183-4033-BF17-ADFAC1CF1EF2
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: TBD
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: pfnUpdateAllocationPropertyCb
req.alt-loc: d3dumddi.h
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
req.typenames: DXGK_PTE
---

# PFND3DDDI_UPDATEALLOCATIONPROPERTYCB callback



## -description
The <b>pfnUpdateAllocationPropertyCb</b> functions updates the property of an allocation without creating a new allocation.



## -prototype

````
PFND3DDDI_UPDATEALLOCATIONPROPERTYCB pfnUpdateAllocationPropertyCb;

__checkReturn HRESULT APIENTRY pfnUpdateAllocationPropertyCb(
  _In_    HANDLE                    hDevice,
  _Inout_ D3DDI_UPDATEALLOCPROPERTY *pUpdateAllocationProperty
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device associated with the allocation


### -param *pUpdateAllocationProperty [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt761856">D3DDDI_UPDATEALLOCPROPERTY</a> structure that describes how to update the allocation with the desired properties.


## -returns
<b>pfnUpdateAllocationPropertyCb</b> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The properties were successfully updated. The driver can start using the allocation with its new property immediately. PagingFenceValue is invalid, though the driver shouldn't wait on it.
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>The request has successfully been queued to VidMm and is being processed. The driver must synchronize against the returned PagingFenceValue before using the allocation with its new property. Note that if the driver request is invalid it may still fail at a later point, in which case the device will be put in error.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>Invalid call with bad arguments provided.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>Desired supported memory segment is full.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>An unknown error has occurred. 

 


## -remarks
