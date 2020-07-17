---
UID: NE:wdfiotarget._WDF_IO_TARGET_OPEN_TYPE
title: _WDF_IO_TARGET_OPEN_TYPE (wdfiotarget.h)
description: The WDF_IO_TARGET_OPEN_TYPE enumeration specifies how a driver identifies a remote I/O target when the driver calls WdfIoTargetOpen.
old-location: wdf\wdf_io_target_open_type.htm
tech.root: wdf
ms.assetid: 27aa5d78-03ce-4fc9-b1c8-d02a760e2787
ms.date: 02/26/2018
keywords: ["_WDF_IO_TARGET_OPEN_TYPE enumeration"]
ms.keywords: DFIOTargetRef_4af14f33-176e-4dca-bf20-1841c834e29b.xml, WDF_IO_TARGET_OPEN_TYPE, WDF_IO_TARGET_OPEN_TYPE enumeration, WdfIoTargetOpenByName, WdfIoTargetOpenLocalTargetByFile, WdfIoTargetOpenReopen, WdfIoTargetOpenUndefined, WdfIoTargetOpenUseExistingDevice, _WDF_IO_TARGET_OPEN_TYPE, kmdf.wdf_io_target_open_type, wdf.wdf_io_target_open_type, wdfiotarget/WDF_IO_TARGET_OPEN_TYPE, wdfiotarget/WdfIoTargetOpenByName, wdfiotarget/WdfIoTargetOpenLocalTargetByFile, wdfiotarget/WdfIoTargetOpenReopen, wdfiotarget/WdfIoTargetOpenUndefined, wdfiotarget/WdfIoTargetOpenUseExistingDevice
f1_keywords:
 - "wdfiotarget/WDF_IO_TARGET_OPEN_TYPE"
 - "WDF_IO_TARGET_OPEN_TYPE"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfiotarget.h
api_name:
- WDF_IO_TARGET_OPEN_TYPE
product:
- Windows
targetos: Windows
req.typenames: WDF_IO_TARGET_OPEN_TYPE
---

# _WDF_IO_TARGET_OPEN_TYPE enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_IO_TARGET_OPEN_TYPE</b> enumeration specifies how a driver identifies a remote I/O target when the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetopen">WdfIoTargetOpen</a>.


## -enum-fields




### -field WdfIoTargetOpenUndefined

Reserved for system use.


### -field WdfIoTargetOpenUseExistingDevice

This value is supported by KMDF only.

The driver is identifying a remote I/O target by supplying a pointer to a Windows Driver Model (WDM) <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure.


### -field WdfIoTargetOpenByName

The driver is opening a remote I/O target by supplying a Unicode name string that represents an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/object-names">object name</a>. This name can identify a device, file, or device interface.


### -field WdfIoTargetOpenReopen

The driver is reopening a remote I/O target after previously calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcloseforqueryremove">WdfIoTargetCloseForQueryRemove</a>. For more information, see the following Remarks section.


### -field WdfIoTargetOpenLocalTargetByFile

This value is supported by UMDF only.

<b>UMDF </b>The driver is opening a file handle that represents the lower stack (just like a local target), so that it can send a driver-created request down to the lower stack. A UMDF driver specifies this value when it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdf_io_target_open_params_init_open_by_file">WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE</a>.


## -remarks



The <b>WDF_IO_TARGET_OPEN_TYPE</b> enumeration is used in the <b>Type</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure.

The driver can specify <b>WdfIoTargetOpenReopen</b> only if it specified <b>WdfIoTargetOpenByName</b> when it originally opened the remote I/O target.

If <b>WdfIoTargetOpenReopen</b> is set, the framework ignores all other members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a> structure and uses the values that the driver specified when it originally called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetopen">WdfIoTargetOpen</a> to open a remote I/O target.

By default (unless the driver specifies <b>UmdfFileObjectPolicy</b>=<b>AllowNullAndUnknownFileObjects</b> in its INF file), UMDF doesn’t allow processing of I/O requests that are not associated with a file object. 
Also, some driver stacks, such as HIDclass-enumerated collection PDOs, fail requests that have no associated file object.

Unlike app-created requests, driver-created requests sent to a local I/O target have no associated file object.  As a result, the framework or the lower driver might fail those requests.

In this situation, you can use <b>WdfIoTargetOpenLocalTargetByFile</b> to cause driver-created requests sent to a local target to be associated with the file object corresponding to that target.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ns-wdfiotarget-_wdf_io_target_open_params">WDF_IO_TARGET_OPEN_PARAMS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdf_io_target_open_params_init_open_by_file">WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcloseforqueryremove">WdfIoTargetCloseForQueryRemove</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetopen">WdfIoTargetOpen</a>
 

 

