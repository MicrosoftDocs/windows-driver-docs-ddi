---
UID: NF:wdfdevice.WDF_IO_TYPE_CONFIG_INIT
title: WDF_IO_TYPE_CONFIG_INIT function
author: windows-driver-content
description: The WDF_IO_TYPE_CONFIG_INIT function initializes a driver's WDF_IO_TYPE_CONFIG structure.
old-location: wdf\wdf_io_type_config_init.htm
old-project: wdf
ms.assetid: 45D60409-EAE5-43A0-9E90-0B2F9FC31840
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_IO_TYPE_CONFIG_INIT function, wdf.wdf_io_type_config_init, WDF_IO_TYPE_CONFIG_INIT, wdfdevice/WDF_IO_TYPE_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.13
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
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
-	WDF_IO_TYPE_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WDF_IO_TYPE_CONFIG_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_IO_TYPE_CONFIG_INIT</b> function initializes a driver's <a href="..\wdfdevice\ns-wdfdevice-_wdf_io_type_config.md">WDF_IO_TYPE_CONFIG</a> structure.


## -syntax


````
void WDF_IO_TYPE_CONFIG_INIT(
  _Out_ PWDF_IO_TYPE_CONFIG IoTypeConfig
);
````


## -parameters




### -param IoTypeConfig [out]

A pointer to a driver-allocated <a href="..\wdfdevice\ns-wdfdevice-_wdf_io_type_config.md">WDF_IO_TYPE_CONFIG</a> structure.


## -returns


This function does not return a value.



## -remarks


The <b>WDF_IO_TYPE_CONFIG_INIT</b> function zeros the specified <a href="..\wdfdevice\ns-wdfdevice-_wdf_io_type_config.md">WDF_IO_TYPE_CONFIG</a> structure and sets the  structure's <b>Size</b> member. It then sets the <b>ReadWriteIoType</b> member to <b>WdfDeviceIoBuffered</b>, and the <b>DeviceControlIoType</b> member to <b>WdfDeviceIoBuffered</b>.



## -see-also

<a href="..\wdfdevice\ns-wdfdevice-_wdf_io_type_config.md">WDF_IO_TYPE_CONFIG</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetiotypeex.md">WdfDeviceInitSetIoTypeEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_IO_TYPE_CONFIG_INIT function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

