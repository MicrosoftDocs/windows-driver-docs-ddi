---
UID: NE:wdfdevice._WDF_REMOVE_LOCK_OPTIONS_FLAGS
title: _WDF_REMOVE_LOCK_OPTIONS_FLAGS (wdfdevice.h)
description: The WDF_REMOVE_LOCK_OPTIONS_FLAGS enumeration type defines flags that are used in a driver's WDF_REMOVE_LOCK_OPTIONS structure.
old-location: wdf\wdf_remove_lock_options_flags.htm
tech.root: wdf
ms.assetid: 3822B8A2-1EFB-45C7-A7DB-FBCE76A06336
ms.date: 02/26/2018
keywords: ["_WDF_REMOVE_LOCK_OPTIONS_FLAGS enumeration"]
ms.keywords: WDF_REMOVE_LOCK_OPTIONS_FLAGS, WDF_REMOVE_LOCK_OPTIONS_FLAGS enumeration, WDF_REMOVE_LOCK_OPTION_ACQUIRE_FOR_IO, _WDF_REMOVE_LOCK_OPTIONS_FLAGS, kmdf.wdf_remove_lock_options_flags, wdf.wdf_remove_lock_options_flags, wdfdevice/WDF_REMOVE_LOCK_OPTIONS_FLAGS, wdfdevice/WDF_REMOVE_LOCK_OPTION_ACQUIRE_FOR_IO
f1_keywords:
 - "wdfdevice/WDF_REMOVE_LOCK_OPTIONS_FLAGS"
 - "WDF_REMOVE_LOCK_OPTIONS_FLAGS"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfdevice.h
api_name:
- WDF_REMOVE_LOCK_OPTIONS_FLAGS
targetos: Windows
req.typenames: WDF_REMOVE_LOCK_OPTIONS_FLAGS
---

# _WDF_REMOVE_LOCK_OPTIONS_FLAGS enumeration


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_REMOVE_LOCK_OPTIONS_FLAGS</b> enumeration type defines flags that are used in a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_remove_lock_options">WDF_REMOVE_LOCK_OPTIONS</a> structure.


## -enum-fields




### -field WDF_REMOVE_LOCK_OPTION_ACQUIRE_FOR_IO

Specifies that the framework should acquire a remove lock before delivering an IRP of any type to the driver.


## -remarks



For more information about using remove locks in a framework-based driver, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetremovelockoptions">WdfDeviceInitSetRemoveLockOptions</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_remove_lock_options">WDF_REMOVE_LOCK_OPTIONS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdf_remove_lock_options_init">WDF_REMOVE_LOCK_OPTIONS_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetremovelockoptions">WdfDeviceInitSetRemoveLockOptions</a>
 

 

