---
UID: NE:wdfdevice._WDF_REMOVE_LOCK_OPTIONS_FLAGS
title: "_WDF_REMOVE_LOCK_OPTIONS_FLAGS"
author: windows-driver-content
description: The WDF_REMOVE_LOCK_OPTIONS_FLAGS enumeration type defines flags that are used in a driver's WDF_REMOVE_LOCK_OPTIONS structure.
old-location: wdf\wdf_remove_lock_options_flags.htm
old-project: wdf
ms.assetid: 3822B8A2-1EFB-45C7-A7DB-FBCE76A06336
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.wdf_remove_lock_options_flags, wdfdevice/WDF_REMOVE_LOCK_OPTION_ACQUIRE_FOR_IO, wdfdevice/WDF_REMOVE_LOCK_OPTIONS_FLAGS, kmdf.wdf_remove_lock_options_flags, WDF_REMOVE_LOCK_OPTIONS_FLAGS, _WDF_REMOVE_LOCK_OPTIONS_FLAGS, WDF_REMOVE_LOCK_OPTIONS_FLAGS enumeration, WDF_REMOVE_LOCK_OPTION_ACQUIRE_FOR_IO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfdevice.h
apiname:
-	WDF_REMOVE_LOCK_OPTIONS_FLAGS
product: Windows
targetos: Windows
req.typenames: WDF_REMOVE_LOCK_OPTIONS_FLAGS
req.product: Windows 10 or later.
---

# _WDF_REMOVE_LOCK_OPTIONS_FLAGS enumeration


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_REMOVE_LOCK_OPTIONS_FLAGS</b> enumeration type defines flags that are used in a driver's <a href="..\wdfdevice\ns-wdfdevice-_wdf_remove_lock_options.md">WDF_REMOVE_LOCK_OPTIONS</a> structure.


## -syntax


````
typedef enum _WDF_REMOVE_LOCK_OPTIONS_FLAGS { 
  WDF_REMOVE_LOCK_OPTION_ACQUIRE_FOR_IO  = 1
} WDF_REMOVE_LOCK_OPTIONS_FLAGS;
````


## -enum-fields




### -field WDF_REMOVE_LOCK_OPTION_ACQUIRE_FOR_IO

Specifies that the framework should acquire a remove lock before delivering an IRP of any type to the driver.


## -remarks



For more information about using remove locks in a framework-based driver, see <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetremovelockoptions.md">WdfDeviceInitSetRemoveLockOptions</a>.




## -see-also

<a href="..\wdfdevice\ns-wdfdevice-_wdf_remove_lock_options.md">WDF_REMOVE_LOCK_OPTIONS</a>



<a href="..\wdfdevice\nf-wdfdevice-wdf_remove_lock_options_init.md">WDF_REMOVE_LOCK_OPTIONS_INIT</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetremovelockoptions.md">WdfDeviceInitSetRemoveLockOptions</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REMOVE_LOCK_OPTIONS_FLAGS enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

