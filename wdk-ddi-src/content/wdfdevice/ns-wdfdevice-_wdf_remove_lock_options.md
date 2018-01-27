---
UID: NS:wdfdevice._WDF_REMOVE_LOCK_OPTIONS
title: _WDF_REMOVE_LOCK_OPTIONS
author: windows-driver-content
description: The WDF_REMOVE_LOCK_OPTIONS structure specifies options for acquiring a remove lock before delivering an IRP to the driver.
old-location: wdf\wdf_remove_lock_options.htm
old-project: wdf
ms.assetid: 0A50C1FB-D0C6-47C4-AD71-AD0B7486AA2E
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PWDF_REMOVE_LOCK_OPTIONS, wdfdevice/WDF_REMOVE_LOCK_OPTIONS, WDF_REMOVE_LOCK_OPTIONS structure, kmdf.wdf_remove_lock_options, *PWDF_REMOVE_LOCK_OPTIONS, wdf.wdf_remove_lock_options, wdfdevice/PWDF_REMOVE_LOCK_OPTIONS, _WDF_REMOVE_LOCK_OPTIONS, PWDF_REMOVE_LOCK_OPTIONS structure pointer, WDF_REMOVE_LOCK_OPTIONS
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	wdfdevice.h
apiname: 
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


## -syntax


````
typedef struct _WDF_REMOVE_LOCK_OPTIONS {
  ULONG Size;
  ULONG Flags;
} WDF_REMOVE_LOCK_OPTIONS, *PWDF_REMOVE_LOCK_OPTIONS;
````


## -struct-fields




### -field Size

The size of the structure, in bytes.


### -field Flags

The bitwise <b>OR</b> of values from the <a href="..\wdfdevice\ne-wdfdevice-_wdf_remove_lock_options_flags.md">WDF_REMOVE_LOCK_OPTIONS_FLAGS</a> enumeration.


## -see-also

<a href="..\wdfdevice\ne-wdfdevice-_wdf_remove_lock_options_flags.md">WDF_REMOVE_LOCK_OPTIONS_FLAGS</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetremovelockoptions.md">WdfDeviceInitSetRemoveLockOptions</a>

<a href="..\wdfdevice\nf-wdfdevice-wdf_remove_lock_options_init.md">WDF_REMOVE_LOCK_OPTIONS_INIT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REMOVE_LOCK_OPTIONS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

