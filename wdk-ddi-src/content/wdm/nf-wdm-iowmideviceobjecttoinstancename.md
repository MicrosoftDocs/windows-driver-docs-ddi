---
UID: NF:wdm.IoWMIDeviceObjectToInstanceName
title: IoWMIDeviceObjectToInstanceName function (wdm.h)
description: The IoWMIDeviceObjectToInstanceName routine determines the instance name for the WMI class instance implemented by the driver that is specified by a device object.
old-location: kernel\iowmideviceobjecttoinstancename.htm
tech.root: kernel
ms.assetid: 18692c0d-8b74-495d-b66a-2873837ff797
ms.date: 04/30/2018
ms.keywords: IoWMIDeviceObjectToInstanceName, IoWMIDeviceObjectToInstanceName routine [Kernel-Mode Driver Architecture], k104_9341dc2b-c948-44bd-891d-a530a8676259.xml, kernel.iowmideviceobjecttoinstancename, wdm/IoWMIDeviceObjectToInstanceName
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoWMIDeviceObjectToInstanceName
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoWMIDeviceObjectToInstanceName function


## -description


The <b>IoWMIDeviceObjectToInstanceName</b> routine determines the instance name for the WMI class instance implemented by the driver that is specified by a device object.


## -parameters




### -param DataBlockObject [in]

Pointer to a WMI data block object. The caller opens the data block object for the WMI class with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iowmiopenblock">IoWMIOpenBlock</a>.


### -param DeviceObject [in]

Specifies a device object. The routine returns the instance name for the driver corresponding to the device object.


### -param InstanceName [out]

Pointer to the <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that the routine uses to return the instance name. The caller frees the returned buffer within <b>UNICODE_STRING</b>.


## -returns



The routine returns an NTSTATUS code. Possible return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation succeeded. The routine stores the instance name in the <b>UNICODE_STRING</b> specified by the <i>InstanceName</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WMI_INSTANCE_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The driver does not implement any instances of the WMI class specified by <i>DataBlockObject</i>.

</td>
</tr>
</table>
 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iowmihandletoinstancename">IoWMIHandleToInstanceName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iowmiopenblock">IoWMIOpenBlock</a>
 

 

