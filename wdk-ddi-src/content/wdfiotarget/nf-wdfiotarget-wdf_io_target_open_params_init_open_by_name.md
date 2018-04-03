---
UID: NF:wdfiotarget.WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_NAME
title: WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_NAME function
author: windows-driver-content
description: The WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_NAME function initializes a driver's WDF_IO_TARGET_OPEN_PARAMS structure so the driver can open an I/O target by specifying the name of the device, file, or device interface.
old-location: wdf\wdf_io_target_open_params_init_open_by_name.htm
old-project: wdf
ms.assetid: e84652c5-a234-4336-92f3-827f965865f8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFIOTargetRef_fd8afc87-6dae-469e-906f-f2fa99aba08e.xml, WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_NAME, WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_NAME function, kmdf.wdf_io_target_open_params_init_open_by_name, wdf.wdf_io_target_open_params_init_open_by_name, wdfiotarget/WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_NAME
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
req.lib: 
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfiotarget.h
api_name:
-	WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_NAME
product:
- Windows
targetos: Windows
req.typenames: WDF_IO_TARGET_STATE, *PWDF_IO_TARGET_STATE
req.product: Windows 10 or later.
---

# WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_NAME function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_NAME</b> function initializes a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552377">WDF_IO_TARGET_OPEN_PARAMS</a> structure so the driver can open an I/O target by specifying the name of the device, file, or device interface. If the supplied name does not exist, the system will not try to create it.


## -parameters




### -param Params [out]

A pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552377">WDF_IO_TARGET_OPEN_PARAMS</a> structure, which the function initializes.


### -param TargetDeviceName [in]

A value for the <b>TargetDeviceName</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552377">WDF_IO_TARGET_OPEN_PARAMS</a> structure. 


### -param DesiredAccess [in]

A value for the <b>DesiredAccess</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552377">WDF_IO_TARGET_OPEN_PARAMS</a> structure.


## -returns



None




## -remarks



If <i>TargetDeviceName</i> specifies the name of a file that already exists, the system opens the existing file. If the file does not exist, the open operation fails.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff552377">WDF_IO_TARGET_OPEN_PARAMS</a> structure is used as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548634">WdfIoTargetOpen</a> method.

The <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_NAME</b> function initializes the <b>Size</b>, <b>Type</b>, <b>TargetDeviceName</b>, <b>DesiredAccess</b>, <b>CreateOptions</b>, and <b>CreateDisposition</b> members of the specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff552377">WDF_IO_TARGET_OPEN_PARAMS</a> structure.


<b>KMDF </b>The <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_NAME</b> function initializes the <b>CreateDisposition</b> member to <b>FILE_OPEN</b>.




<b>UMDF </b>The <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_NAME</b> function initializes the <b>CreateDisposition</b> member to <b>OPEN_EXISTING</b>.



For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.


#### Examples

For a code example that uses <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_NAME</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff548634">WdfIoTargetOpen</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552377">WDF_IO_TARGET_OPEN_PARAMS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552378">WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552380">WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548634">WdfIoTargetOpen</a>
 

 

