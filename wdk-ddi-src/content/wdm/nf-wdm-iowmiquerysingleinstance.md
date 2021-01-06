---
UID: NF:wdm.IoWMIQuerySingleInstance
title: IoWMIQuerySingleInstance function (wdm.h)
description: The IoWMIQuerySingleInstance routine returns the specified instance of a WMI data block.
old-location: kernel\iowmiquerysingleinstance.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["IoWMIQuerySingleInstance function"]
ms.keywords: IoWMIQuerySingleInstance, IoWMIQuerySingleInstance routine [Kernel-Mode Driver Architecture], k104_ef4cfbd8-cca3-4ec0-99cd-3715c2ddf52f.xml, kernel.iowmiquerysingleinstance, wdm/IoWMIQuerySingleInstance
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IoWMIQuerySingleInstance
 - wdm/IoWMIQuerySingleInstance
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoWMIQuerySingleInstance
---

# IoWMIQuerySingleInstance function


## -description

The <b>IoWMIQuerySingleInstance</b> routine returns the specified instance of a WMI data block.

## -parameters

### -param DataBlockObject 

[in]
Pointer to a WMI data block object. The caller opens the data block object for the WMI class with the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmiopenblock">IoWMIOpenBlock</a> routine. The object must be opened with the WMIGUID_QUERY access right.

### -param InstanceName 

[in]
Specifies the name of the instance of the data block. This value corresponds to the value of the <b>InstanceName</b> property for the block.

### -param InOutBufferSize 

[in, out]
Pointer to a memory location that specifies the size of the buffer passed in the <i>OutBuffer</i> parameter. If the routine succeeds, it updates the memory location to specify the number of bytes actually stored in <i>OutBuffer</i>. If the routine fails with status code of STATUS_BUFFER_TOO_SMALL, it returns the number of bytes required to return the data.

### -param OutBuffer 

[out, optional]
Pointer to the buffer where the routine returns the WMI data. The routine returns a variable-sized <a href="/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_single_instance">WNODE_SINGLE_INSTANCE</a> structure. <i>OutBuffer</i> must point to a buffer allocated from nonpaged pool.

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
The operation succeeded. The routine returns the WMI data in the buffer pointed to by the <i>OutBuffer</i> parameter. The routine also returns the size, in bytes, of the returned data in the memory location pointed to by the <i>InOutBufferSize</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WMI_GUID_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
No drivers implement the specified WMI class.

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
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer passed by the caller in the <i>OutBuffer</i> parameter is too small. The routine returns the required buffer size in the memory location pointed to by the <i>InOutBufferSize</i> parameter.

</td>
</tr>
</table>

## -remarks

<b>IoWMIQuerySingleInstance</b> determines which drivers might support the specified WMI class with the specified instance name, and issues an <a href="/windows-hardware/drivers/kernel/irp-mn-query-single-instance">IRP_MN_QUERY_SINGLE_INSTANCE</a> request to each such driver. The driver that exports the data block instance with matching <b>InstanceName</b> property returns the appropriate data.

To query for multiple WMI classes and instance names, use the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmiquerysingleinstancemultiple">IoWMIQuerySingleInstanceMultiple</a> routine. Drivers can use the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmisetsingleinstance">IoWMISetSingleInstance</a> routine to update the class instance.

## -see-also

<a href="/windows-hardware/drivers/kernel/irp-mn-query-single-instance">IRP_MN_QUERY_SINGLE_INSTANCE</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmiopenblock">IoWMIOpenBlock</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmiquerysingleinstancemultiple">IoWMIQuerySingleInstanceMultiple</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmisetsingleinstance">IoWMISetSingleInstance</a>
