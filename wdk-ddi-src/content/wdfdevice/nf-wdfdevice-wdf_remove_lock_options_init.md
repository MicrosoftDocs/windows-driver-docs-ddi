---
UID: NF:wdfdevice.WDF_REMOVE_LOCK_OPTIONS_INIT
title: WDF_REMOVE_LOCK_OPTIONS_INIT function (wdfdevice.h)
description: The WDF_REMOVE_LOCK_OPTIONS_INIT function initializes a WDF_REMOVE_LOCK_OPTIONS structure.
old-location: wdf\wdf_remove_lock_options_init.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_REMOVE_LOCK_OPTIONS_INIT function"]
ms.keywords: WDF_REMOVE_LOCK_OPTIONS_INIT, WDF_REMOVE_LOCK_OPTIONS_INIT function, kmdf.wdf_remove_lock_options_init, wdf.wdf_remove_lock_options_init, wdfdevice/WDF_REMOVE_LOCK_OPTIONS_INIT
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WDF_REMOVE_LOCK_OPTIONS_INIT
 - wdfdevice/WDF_REMOVE_LOCK_OPTIONS_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfdevice.h
api_name:
 - WDF_REMOVE_LOCK_OPTIONS_INIT
---

# WDF_REMOVE_LOCK_OPTIONS_INIT function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>


   The 
  <b>WDF_REMOVE_LOCK_OPTIONS_INIT</b> function initializes a <a href="/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_remove_lock_options">WDF_REMOVE_LOCK_OPTIONS</a> structure.

## -parameters

### -param RemoveLockOptions [out]


A pointer to a <a href="/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_remove_lock_options">WDF_REMOVE_LOCK_OPTIONS</a> structure.

### -param Flags [in]



<a href="/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_remove_lock_options_flags">WDF_REMOVE_LOCK_OPTIONS_FLAGS</a>-typed flags.

## -remarks

The <b>WDF_REMOVE_LOCK_OPTIONS_INIT</b> function zeros the <a href="/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_remove_lock_options">WDF_REMOVE_LOCK_OPTIONS</a> structure that the <i>RemoveLockOptions</i> parameter specifies and sets its <b>Size</b> member. This function also sets the structure's <b>Flags</b> member to the value provided in the <i>Flags</i> parameter.

Before a driver calls <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetremovelockoptions">WdfDeviceInitSetRemoveLockOptions</a>, it must call <b>WDF_REMOVE_LOCK_OPTIONS_INIT</b> to initialize a <a href="/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_remove_lock_options">WDF_REMOVE_LOCK_OPTIONS</a> structure.

For a code example that uses <b>WDF_REMOVE_LOCK_OPTIONS_INIT</b>, see <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetremovelockoptions">WdfDeviceInitSetRemoveLockOptions</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_remove_lock_options">WDF_REMOVE_LOCK_OPTIONS</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_remove_lock_options_flags">WDF_REMOVE_LOCK_OPTIONS_FLAGS</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetremovelockoptions">WdfDeviceInitSetRemoveLockOptions</a>
