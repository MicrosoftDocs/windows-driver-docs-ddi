---
UID: NC:dispmprt.DXGKDDI_EXCHANGEPRESTARTINFO
title: DXGKDDI_EXCHANGEPRESTARTINFO (dispmprt.h)
description: Allows very simple data to be exchanged between the OS and driver which may be required prior to DxgkDdiStartDevice device being called and therefore cannot be queried through normal caps or adapter info DDIs.
old-location: display\dxgkddi_exchangeprestartinfo.htm
tech.root: display
ms.assetid: B23EDC08-18E4-4826-AC51-163C706D4F43
ms.date: 04/16/2018
keywords: ["DXGKDDI_EXCHANGEPRESTARTINFO callback function"]
ms.keywords: DXGKDDI_EXCHANGEPRESTARTINFO, DXGKDDI_EXCHANGEPRESTARTINFO callback, DXGKDDI_EXCHANGEPRESTARTINFO callback function [Display Devices], display.dxgkddi_exchangeprestartinfo, dispmprt/DXGKDDI_EXCHANGEPRESTARTINFO
req.header: dispmprt.h
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
 - DXGKDDI_EXCHANGEPRESTARTINFO
 - dispmprt/DXGKDDI_EXCHANGEPRESTARTINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_EXCHANGEPRESTARTINFO
---

# DXGKDDI_EXCHANGEPRESTARTINFO callback function


## -description

Allows very simple data to be exchanged between the OS and driver which may be required prior to DxgkDdiStartDevice device being called and therefore cannot be queried through normal caps or adapter info DDIs.

## -parameters

### -param hAdapter

[in] Identifies the adapter.

### -param pPreStartInfo

[in] Pointer to a [DXGK_PRE_START_INFO](ns-dispmprt-_dxgk_pre_start_info.md) structure, which contains both fields for the OS to pass info and fields for the driver to return info. Initially, only *SupportPreserveBootDisplay* is defined.

[out] SupportPreserveBootDisplay

The driver and hardware support the requirements that allow the boot frame buffer to be used and displayed throughout the hardware initialization, performed during [DxgkDdiStartDevice](nc-dispmprt-dxgkddi_start_device.md).

## -returns

If this routine succeeds and returns the requested change, it returns STATUS_SUCCESS.

## -remarks

This DDI will be called after [DxgkDdiAddDevice](nc-dispmprt-dxgkddi_add_device.md) and before [DxgkDdiStartDevice](nc-dispmprt-dxgkddi_start_device.md) so that the driver does not have access to its own hardware resources. However, it can use the *PhysicalDeviceObject* passed to the driver in **DxgkDdiAddDevice** to call [IoGetDeviceProperty](../wdm/nf-wdm-iogetdeviceproperty.md). For example, it can find the hardware id in order to decide what to return in the output fields of the DXGK_PRE_START_INFO structure.



This function is always called at PASSIVE level so the supporting code should be made pageable where possible.