---
UID: NF:wdm.IoWMIHandleToInstanceName
title: IoWMIHandleToInstanceName function (wdm.h)
description: The IoWMIHandleToInstanceName routine determines the instance name for the WMI class instance implemented by the driver that is specified by a file handle.
old-location: kernel\iowmihandletoinstancename.htm
tech.root: kernel
ms.assetid: e9d8fde5-81b7-480b-8d7c-0005fd1868fb
ms.date: 04/30/2018
ms.keywords: IoWMIHandleToInstanceName, IoWMIHandleToInstanceName routine [Kernel-Mode Driver Architecture], k104_7d97f756-2f7f-4788-bcbc-368e08b6b86f.xml, kernel.iowmihandletoinstancename, wdm/IoWMIHandleToInstanceName
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
- IoWMIHandleToInstanceName
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoWMIHandleToInstanceName function


## -description


The <b>IoWMIHandleToInstanceName</b> routine determines the instance name for the WMI class instance implemented by the driver that is specified by a file handle.


## -parameters




### -param DataBlockObject [in]

Pointer to a WMI data block object. The caller opens the data block object for the WMI class with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iowmiopenblock">IoWMIOpenBlock</a> routine. 


### -param FileHandle [in]

Specifies a file handle. The routine returns the instance name corresponding to the driver that is represented by the file handle. 


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
The operation succeeded. The routine fills the <b>UNICODE_STRING</b> structure pointed to by the <i>InstanceName</i> parameter with the instance name.

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



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iowmideviceobjecttoinstancename">IoWMIDeviceObjectToInstanceName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iowmiopenblock">IoWMIOpenBlock</a>
 

 

