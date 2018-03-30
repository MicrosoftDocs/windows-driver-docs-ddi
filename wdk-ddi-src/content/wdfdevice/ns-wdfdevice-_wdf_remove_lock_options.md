---
UID: NS:wdfdevice._WDF_REMOVE_LOCK_OPTIONS
title: "_WDF_REMOVE_LOCK_OPTIONS"
author: windows-driver-content
description: The WDF_REMOVE_LOCK_OPTIONS structure specifies options for acquiring a remove lock before delivering an IRP to the driver.
old-location: wdf\wdf_remove_lock_options.htm
old-project: wdf
ms.assetid: 0A50C1FB-D0C6-47C4-AD71-AD0B7486AA2E
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_REMOVE_LOCK_OPTIONS, PWDF_REMOVE_LOCK_OPTIONS, PWDF_REMOVE_LOCK_OPTIONS structure pointer, WDF_REMOVE_LOCK_OPTIONS, WDF_REMOVE_LOCK_OPTIONS structure, _WDF_REMOVE_LOCK_OPTIONS, kmdf.wdf_remove_lock_options, wdf.wdf_remove_lock_options, wdfdevice/PWDF_REMOVE_LOCK_OPTIONS, wdfdevice/WDF_REMOVE_LOCK_OPTIONS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfdevice.h
api_name:
-	WDF_REMOVE_LOCK_OPTIONS
product: Windows
targetos: Windows
req.typenames: WDF_REMOVE_LOCK_OPTIONS, *PWDF_REMOVE_LOCK_OPTIONS
req.product: Windows 10 or later.
---

# _WDF_REMOVE_LOCK_OPTIONS structure


## -description


<p class="CCE_Message">[Applies to KMDF only]


   The <b>WDF_REMOVE_LOCK_OPTIONS</b> structure specifies options for acquiring a remove lock before delivering an IRP to the driver.


## -struct-fields




### -field Size

The size of the structure, in bytes.


### -field Flags

The bitwise <b>OR</b> of values from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406498">WDF_REMOVE_LOCK_OPTIONS_FLAGS</a> enumeration.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406498">WDF_REMOVE_LOCK_OPTIONS_FLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406501">WDF_REMOVE_LOCK_OPTIONS_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451095">WdfDeviceInitSetRemoveLockOptions</a>
 

 

