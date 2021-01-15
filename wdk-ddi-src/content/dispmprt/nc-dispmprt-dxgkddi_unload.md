---
UID: NC:dispmprt.DXGKDDI_UNLOAD
title: DXGKDDI_UNLOAD (dispmprt.h)
description: The DxgkDdiUnload function frees any resources allocated during execution of the display miniport driver's DriverEntry function.
old-location: display\dxgkddiunload.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXGKDDI_UNLOAD callback function"]
ms.keywords: DXGKDDI_UNLOAD, DXGKDDI_UNLOAD callback, DmFunctions_b7f60489-c7e7-4bd1-bf17-ff193bc7d614.xml, DxgkDdiUnload, DxgkDdiUnload callback function [Display Devices], display.dxgkddiunload, dispmprt/DxgkDdiUnload
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - DXGKDDI_UNLOAD
 - dispmprt/DXGKDDI_UNLOAD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Dispmprt.h
api_name:
 - DXGKDDI_UNLOAD
---

# DXGKDDI_UNLOAD callback function


## -description

The <i>DxgkDdiUnload</i> function frees any resources allocated during execution of the display miniport driver's <a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> function.

## -remarks

Typically, there will be nothing to do in <i>DxgkDdiUnload</i>.

<i>DxgkDdiUnload</i> should be made pageable.

## -see-also

<a href="/windows-hardware/drivers/display/driverentry-of-display-miniport-driver">DriverEntry of Display Miniport Driver</a>

