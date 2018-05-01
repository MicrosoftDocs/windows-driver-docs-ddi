---
UID: NF:wdfdevice.WDF_REMOVE_LOCK_OPTIONS_INIT
title: WDF_REMOVE_LOCK_OPTIONS_INIT function
author: windows-driver-content
description: The WDF_REMOVE_LOCK_OPTIONS_INIT function initializes a WDF_REMOVE_LOCK_OPTIONS structure.
old-location: wdf\wdf_remove_lock_options_init.htm
old-project: wdf
ms.assetid: 08D0CE94-E37E-4BAE-99C8-FB4EDF7BCDDB
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WDF_REMOVE_LOCK_OPTIONS_INIT, WDF_REMOVE_LOCK_OPTIONS_INIT function, kmdf.wdf_remove_lock_options_init, wdf.wdf_remove_lock_options_init, wdfdevice/WDF_REMOVE_LOCK_OPTIONS_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfdevice.h
api_name:
-	WDF_REMOVE_LOCK_OPTIONS_INIT
product: Windows
targetos: Windows
req.typenames: 
---

# WDF_REMOVE_LOCK_OPTIONS_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF only]


   The 
  <b>WDF_REMOVE_LOCK_OPTIONS_INIT</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406495">WDF_REMOVE_LOCK_OPTIONS</a> structure.


## -parameters




### -param RemoveLockOptions [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406495">WDF_REMOVE_LOCK_OPTIONS</a> structure.


### -param Flags [in]


<a href="https://msdn.microsoft.com/library/windows/hardware/hh406498">WDF_REMOVE_LOCK_OPTIONS_FLAGS</a>-typed flags.


## -returns



This function does not return a value.




## -remarks



The <b>WDF_REMOVE_LOCK_OPTIONS_INIT</b> function zeros the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406495">WDF_REMOVE_LOCK_OPTIONS</a> structure that the <i>RemoveLockOptions</i> parameter specifies and sets its <b>Size</b> member. This function also sets the structure's <b>Flags</b> member to the value provided in the <i>Flags</i> parameter.

Before a driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/hh451095">WdfDeviceInitSetRemoveLockOptions</a>, it must call <b>WDF_REMOVE_LOCK_OPTIONS_INIT</b> to initialize a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406495">WDF_REMOVE_LOCK_OPTIONS</a> structure.

For a code example that uses <b>WDF_REMOVE_LOCK_OPTIONS_INIT</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh451095">WdfDeviceInitSetRemoveLockOptions</a>.






## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406495">WDF_REMOVE_LOCK_OPTIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406498">WDF_REMOVE_LOCK_OPTIONS_FLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451095">WdfDeviceInitSetRemoveLockOptions</a>
 

 

