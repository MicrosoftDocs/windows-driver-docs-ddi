---
UID: NE:wdfiotarget._WDF_IO_TARGET_OPEN_TYPE
title: "_WDF_IO_TARGET_OPEN_TYPE"
author: windows-driver-content
description: The WDF_IO_TARGET_OPEN_TYPE enumeration specifies how a driver identifies a remote I/O target when the driver calls WdfIoTargetOpen.
old-location: wdf\wdf_io_target_open_type.htm
old-project: wdf
ms.assetid: 27aa5d78-03ce-4fc9-b1c8-d02a760e2787
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFIOTargetRef_4af14f33-176e-4dca-bf20-1841c834e29b.xml, WDF_IO_TARGET_OPEN_TYPE, WDF_IO_TARGET_OPEN_TYPE enumeration, WdfIoTargetOpenByName, WdfIoTargetOpenLocalTargetByFile, WdfIoTargetOpenReopen, WdfIoTargetOpenUndefined, WdfIoTargetOpenUseExistingDevice, _WDF_IO_TARGET_OPEN_TYPE, kmdf.wdf_io_target_open_type, wdf.wdf_io_target_open_type, wdfiotarget/WDF_IO_TARGET_OPEN_TYPE, wdfiotarget/WdfIoTargetOpenByName, wdfiotarget/WdfIoTargetOpenLocalTargetByFile, wdfiotarget/WdfIoTargetOpenReopen, wdfiotarget/WdfIoTargetOpenUndefined, wdfiotarget/WdfIoTargetOpenUseExistingDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfiotarget.h
api_name:
-	WDF_IO_TARGET_OPEN_TYPE
product: Windows
targetos: Windows
req.typenames: WDF_IO_TARGET_OPEN_TYPE
req.product: Windows 10 or later.
---

# _WDF_IO_TARGET_OPEN_TYPE enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_IO_TARGET_OPEN_TYPE</b> enumeration specifies how a driver identifies a remote I/O target when the driver calls <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetopen.md">WdfIoTargetOpen</a>.


## -syntax


````
typedef enum _WDF_IO_TARGET_OPEN_TYPE { 
  WdfIoTargetOpenUndefined          = 0,
  WdfIoTargetOpenUseExistingDevice  = 1,
  WdfIoTargetOpenByName             = 2,
  WdfIoTargetOpenReopen             = 3,
  WdfIoTargetOpenLocalTargetByFile  = 4
} WDF_IO_TARGET_OPEN_TYPE;
````


## -enum-fields




### -field WdfIoTargetOpenUndefined

Reserved for system use.


### -field WdfIoTargetOpenUseExistingDevice

This value is supported by KMDF only.

The driver is identifying a remote I/O target by supplying a pointer to a Windows Driver Model (WDM) <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure.


### -field WdfIoTargetOpenByName

The driver is opening a remote I/O target by supplying a Unicode name string that represents an <a href="https://msdn.microsoft.com/b30e7475-7f94-4993-b373-8e4a8b1bcb4c">object name</a>. This name can identify a device, file, or device interface.


### -field WdfIoTargetOpenReopen

The driver is reopening a remote I/O target after previously calling <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcloseforqueryremove.md">WdfIoTargetCloseForQueryRemove</a>. For more information, see the following Remarks section.


### -field WdfIoTargetOpenLocalTargetByFile

This value is supported by UMDF only.

<b>UMDF </b>The driver is opening a file handle that represents the lower stack (just like a local target), so that it can send a driver-created request down to the lower stack. A UMDF driver specifies this value when it calls <a href="..\wdfiotarget\nf-wdfiotarget-wdf_io_target_open_params_init_open_by_file.md">WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE</a>.


## -remarks



The <b>WDF_IO_TARGET_OPEN_TYPE</b> enumeration is used in the <b>Type</b> member of the <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure.

The driver can specify <b>WdfIoTargetOpenReopen</b> only if it specified <b>WdfIoTargetOpenByName</b> when it originally opened the remote I/O target.

If <b>WdfIoTargetOpenReopen</b> is set, the framework ignores all other members of the <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure and uses the values that the driver specified when it originally called <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetopen.md">WdfIoTargetOpen</a> to open a remote I/O target.

By default (unless the driver specifies <b>UmdfFileObjectPolicy</b>=<b>AllowNullAndUnknownFileObjects</b> in its INF file), UMDF doesn’t allow processing of I/O requests that are not associated with a file object. 
Also, some driver stacks, such as HIDclass-enumerated collection PDOs, fail requests that have no associated file object.

Unlike app-created requests, driver-created requests sent to a local I/O target have no associated file object.  As a result, the framework or the lower driver might fail those requests.

In this situation, you can use <b>WdfIoTargetOpenLocalTargetByFile</b> to cause driver-created requests sent to a local target to be associated with the file object corresponding to that target.




## -see-also

<a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdf_io_target_open_params_init_open_by_file.md">WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetopen.md">WdfIoTargetOpen</a>



<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcloseforqueryremove.md">WdfIoTargetCloseForQueryRemove</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_IO_TARGET_OPEN_TYPE enumeration%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

