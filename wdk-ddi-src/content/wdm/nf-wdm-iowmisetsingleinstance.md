---
UID: NF:wdm.IoWMISetSingleInstance
title: IoWMISetSingleInstance function (wdm.h)
description: The IoWMISetSingleInstance routine sets the values for properties within the data block instance that matches the specified WMI class and instance name.
old-location: kernel\iowmisetsingleinstance.htm
tech.root: kernel
ms.assetid: 043b51cd-816f-414d-85b2-2573c42393e4
ms.date: 04/30/2018
keywords: ["IoWMISetSingleInstance function"]
ms.keywords: IoWMISetSingleInstance, IoWMISetSingleInstance routine [Kernel-Mode Driver Architecture], k104_35479ad6-0f12-4d8b-b375-faa271cf65fd.xml, kernel.iowmisetsingleinstance, wdm/IoWMISetSingleInstance
f1_keywords:
 - "wdm/IoWMISetSingleInstance"
 - "IoWMISetSingleInstance"
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoWMISetSingleInstance
targetos: Windows
req.typenames: 
---

# IoWMISetSingleInstance function


## -description


The <b>IoWMISetSingleInstance</b> routine sets the values for properties within the data block instance that matches the specified WMI class and instance name.


## -parameters




### -param DataBlockObject [in]

Pointer to a WMI data block object. The caller opens the data block object for the WMI class with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmiopenblock">IoWMIOpenBlock</a> routine. The object must be opened with the WMIGUID_SET access right. 


### -param InstanceName [in]

Specifies the name of the instance of the data block. This value corresponds to the value of the <b>InstanceName</b> property for the block.


### -param Version [in]

Reserved for future use. Callers must set this parameter to zero.


### -param ValueBufferSize [in]

Specifies the size, in bytes, of the buffer passed in the <i>ValueBuffer</i> parameter.


### -param ValueBuffer [in]

Pointer to the buffer that contains the new values for the properties within the data block.


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
The operation succeeded. The values of the WMI data block instance properties are updated to the contents of the buffer pointed to by the <i>ValueBuffer</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WMI_GUID_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
No drivers implement the WMI class.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WMI_INSTANCE_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
No driver implements an instance of the WMI class with <b>InstanceName</b> property equal to the value specified in the <i>InstanceName</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WMI_READ_ONLY</b></dt>
</dl>
</td>
<td width="60%">
All properties of the WMI class are read-only.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WMI_SET_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
The driver that implements the WMI data block instance is unable to update the instance.

</td>
</tr>
</table>
 




## -remarks



<b>IoWMISetSingleInstance</b> determines which drivers might support the specified WMI class and instance name, and issues an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-change-single-instance">IRP_MN_CHANGE_SINGLE_INSTANCE</a> request to each such driver. The driver that exports the data block instance with matching <b>InstanceName</b> property updates its data block instance. Note that a data block might have both read-only and read/write properties. In this case, only the read/write properties will be updated and STATUS_SUCCESS is returned.

Drivers can also use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmisetsingleitem">IoWMISetSingleItem</a> routine to update a single property within the class instance.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-change-single-instance">IRP_MN_CHANGE_SINGLE_INSTANCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmiopenblock">IoWMIOpenBlock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmiquerysingleinstance">IoWMIQuerySingleInstance</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmisetsingleitem">IoWMISetSingleItem</a>
 

 

