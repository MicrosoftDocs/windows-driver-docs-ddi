---
UID: NF:wdfiotarget.WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME
title: WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME function
author: windows-driver-content
description: The WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME function initializes a driver's WDF_IO_TARGET_OPEN_PARAMS structure so the driver can open an I/O target by specifying the name of the device, file, or device interface.
old-location: wdf\wdf_io_target_open_params_init_create_by_name.htm
old-project: wdf
ms.assetid: f6a6726a-83bc-4102-a6b6-74115ca4b889
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME, DFIOTargetRef_5ae50d6e-6e3b-484a-afe9-6198860180b7.xml, WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME function, kmdf.wdf_io_target_open_params_init_create_by_name, wdf.wdf_io_target_open_params_init_create_by_name, wdfiotarget/WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Universal
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfiotarget.h
apiname:
-	WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME
product: Windows
targetos: Windows
req.typenames: "*PWDF_IO_TARGET_STATE, WDF_IO_TARGET_STATE"
req.product: Windows 10 or later.
---

# WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME</b> function initializes a driver's <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure so the driver can open an I/O target by specifying the name of the device, file, or device interface. If the supplied name does not exist, the operating system will try to create it.


## -syntax


````
VOID WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME(
  _Out_ PWDF_IO_TARGET_OPEN_PARAMS Params,
  _In_  PCUNICODE_STRING           TargetDeviceName,
  _In_  ACCESS_MASK                DesiredAccess
);
````


## -parameters




#### - Params [out]

A pointer to a driver-allocated <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure, which the function initializes.


#### - TargetDeviceName [in]

A value for the <b>TargetDeviceName</b> member of the <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure. 


#### - DesiredAccess [in]

A value for the <b>DesiredAccess</b> member of the <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure.


## -returns


None



## -remarks


If <i>TargetDeviceName</i> specifies the name of a file that already exists, the system replaces the existing file. If the file does not exist, the system creates it.

The <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure is used as input to the <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetopen.md">WdfIoTargetOpen</a> method.


<b>KMDF </b>The <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME</b> function initializes the <b>Size</b>, <b>Type</b>, <b>TargetDeviceName</b>, <b>DesiredAccess</b>, and <b>CreateOptions</b> members of the specified <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure.




<b>UMDF </b>The <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME</b> function initializes the <b>Size</b>, <b>Type</b>, <b>DesiredAccess</b>, and <b>TargetDeviceName</b>  members of the specified <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure. It sets the <b>ShareAccess</b> member to zero. It also sets the <b>FileAttributes</b> member to <b>FILE_ATTRIBUTE_NORMAL</b>.



For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.



## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetopen.md">WdfIoTargetOpen</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdf_io_target_open_params_init_open_by_name.md">WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_NAME</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdf_io_target_open_params_init_existing_device.md">WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE</a>

<a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

