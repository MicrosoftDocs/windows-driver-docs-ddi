---
UID: NC:d3dumddi.PFND3DDDI_DESTROYDEVICE
title: PFND3DDDI_DESTROYDEVICE (d3dumddi.h)
description: The DestroyDevice function destroys a graphics context.
old-location: display\destroydevice.htm
tech.root: display
ms.assetid: a3c158c2-6c0d-4da0-80f4-569971b10673
ms.date: 05/10/2018
ms.keywords: DestroyDevice, DestroyDevice callback function [Display Devices], PFND3DDDI_DESTROYDEVICE, PFND3DDDI_DESTROYDEVICE callback, UserModeDisplayDriver_Functions_4d34f924-8742-4957-b3f0-d4a63d338ada.xml, d3dumddi/DestroyDevice, display.destroydevice
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
 - "d3dumddi/DestroyDevice"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - DestroyDevice
product:
 - Windows
---

# PFND3DDDI_DESTROYDEVICE callback function

## -description

The <i>DestroyDevice</i> function destroys a graphics context.

## -parameters

### -param hDevice

A handle to the display device (graphics context) being destroyed.

## -returns

<i>DestroyDevice</i> returns S_OK or an appropriate error result.

## -remarks

The driver should free all of the resources that it allocated for the device and clean up any internal tracking data structures. 

Before the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_deallocatecb">pfnDeallocateCb</a> function to release allocations, the driver must ensure that the allocations are unlocked. In other words, in the lifetime of a device, every call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockcb">pfnLockCb</a> function to lock an allocation must be paired with a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_unlockcb">pfnUnlockCb</a> function to unlock the allocation. However, in one call to <i>pfnUnlockCb</i>, the driver can unlock multiple allocations that were each allocated in separate <i>pfnLockCb</i> calls.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createdevice">CreateDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_deallocatecb">pfnDeallocateCb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockcb">pfnLockCb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_unlockcb">pfnUnlockCb</a>

