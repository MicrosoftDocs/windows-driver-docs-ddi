---
UID: NC:dispmprt.DXGKDDI_EXCHANGEPRESTARTINFO
title: DXGKDDI_EXCHANGEPRESTARTINFO
author: windows-driver-content
description: Allows very simple data to be exchanged between the OS and driver which may be required prior to DxgkDdiStartDevice device being called and therefore cannot be queried through normal caps or adapter info DDIs.
old-location: display\dxgkddi_exchangeprestartinfo.htm
old-project: display
ms.assetid: B23EDC08-18E4-4826-AC51-163C706D4F43
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _SYMBOL_INFO_EX, *PSYMBOL_INFO_EX, SYMBOL_INFO_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKDDI_EXCHANGEPRESTARTINFO
req.alt-loc: dispmprt.h
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
req.typenames: *PSYMBOL_INFO_EX, SYMBOL_INFO_EX
---

# DXGKDDI_EXCHANGEPRESTARTINFO callback



## -description
Allows very simple data to be exchanged between the OS and driver which may be required prior to DxgkDdiStartDevice device being called and therefore cannot be queried through normal caps or adapter info DDIs.



## -prototype

````
NTSTATUS APIENTRY DXGKDDI_EXCHANGEPRESTARTINFO(
  _In_    const Handle               hAdapter,
  _Inout_       PDXGK_PRE_START_INFO pPreStartInfo
);
````


## -parameters

### -param hAdapter [in]

[in] Identifies the adapter.


### -param pPreStartInfo [in, out]

[in] Pointer to a DXGK_PRE_START_INFO structure which contains both fields for the OS to pass info and fields for the driver to return info.  Only SupportPreserveBootDisplay is defined initially.

[out] SupportPreserveBootDisplay

The driver and hardware support the requirements to allow the boot frame buffer to be used and displayed throughout the hardware initialization performed during DxgkDdiStartDevice.


## -returns
If this routine succeeds and returns the requested change, it returns STATUS_SUCCESS.


## -remarks
This DDI will be called after DxgkDdiAddDevice and before DxgkDdiStartDevice so the driver does not have access to its own hardware resources yet however it can use the PhysicalDeviceObject passed to the driver in DxgkDdiAddDevice to call IoGetDeviceProperty, for example to find the hardware id to decide what to return in the output fields of the DXGK_PRE_START_INFO structure.

 

This function is always called at PASSIVE level so the supporting code should be made pageable where possible.
</p>