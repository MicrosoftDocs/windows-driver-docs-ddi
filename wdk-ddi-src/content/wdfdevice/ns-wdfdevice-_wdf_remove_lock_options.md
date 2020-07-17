---
UID: NS:wdfdevice._WDF_REMOVE_LOCK_OPTIONS
title: _WDF_REMOVE_LOCK_OPTIONS (wdfdevice.h)
description: The WDF_REMOVE_LOCK_OPTIONS structure specifies options for acquiring a remove lock before delivering an IRP to the driver.
old-location: wdf\wdf_remove_lock_options.htm
tech.root: wdf
ms.assetid: 0A50C1FB-D0C6-47C4-AD71-AD0B7486AA2E
ms.date: 02/26/2018
keywords: ["_WDF_REMOVE_LOCK_OPTIONS structure"]
ms.keywords: "*PWDF_REMOVE_LOCK_OPTIONS, PWDF_REMOVE_LOCK_OPTIONS, PWDF_REMOVE_LOCK_OPTIONS structure pointer, WDF_REMOVE_LOCK_OPTIONS, WDF_REMOVE_LOCK_OPTIONS structure, _WDF_REMOVE_LOCK_OPTIONS, kmdf.wdf_remove_lock_options, wdf.wdf_remove_lock_options, wdfdevice/PWDF_REMOVE_LOCK_OPTIONS, wdfdevice/WDF_REMOVE_LOCK_OPTIONS"
f1_keywords:
 - "wdfdevice/WDF_REMOVE_LOCK_OPTIONS"
 - "WDF_REMOVE_LOCK_OPTIONS"
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
- WDF_REMOVE_LOCK_OPTIONS
product:
- Windows
targetos: Windows
req.typenames: WDF_REMOVE_LOCK_OPTIONS, *PWDF_REMOVE_LOCK_OPTIONS
---

# _WDF_REMOVE_LOCK_OPTIONS structure


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>


   The <b>WDF_REMOVE_LOCK_OPTIONS</b> structure specifies options for acquiring a remove lock before delivering an IRP to the driver.


## -struct-fields




### -field Size

The size of the structure, in bytes.


### -field Flags

The bitwise <b>OR</b> of values from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_remove_lock_options_flags">WDF_REMOVE_LOCK_OPTIONS_FLAGS</a> enumeration.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_remove_lock_options_flags">WDF_REMOVE_LOCK_OPTIONS_FLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdf_remove_lock_options_init">WDF_REMOVE_LOCK_OPTIONS_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetremovelockoptions">WdfDeviceInitSetRemoveLockOptions</a>
 

 

