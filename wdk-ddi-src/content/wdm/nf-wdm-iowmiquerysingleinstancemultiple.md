---
UID: NF:wdm.IoWMIQuerySingleInstanceMultiple
title: IoWMIQuerySingleInstanceMultiple function (wdm.h)
description: The IoWMIQuerySingleInstanceMultiple routine returns all WMI data block instances that implement the specified WMI classes with the specified instance names.
old-location: kernel\iowmiquerysingleinstancemultiple.htm
tech.root: kernel
ms.assetid: c0e011b5-804c-4f0d-a125-a083a0f83d50
ms.date: 04/30/2018
keywords: ["IoWMIQuerySingleInstanceMultiple function"]
ms.keywords: IoWMIQuerySingleInstanceMultiple, IoWMIQuerySingleInstanceMultiple routine [Kernel-Mode Driver Architecture], k104_bd0dace0-1c4b-4e21-9e2c-7c3060878881.xml, kernel.iowmiquerysingleinstancemultiple, wdm/IoWMIQuerySingleInstanceMultiple
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
 - IoWMIQuerySingleInstanceMultiple
 - wdm/IoWMIQuerySingleInstanceMultiple
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoWMIQuerySingleInstanceMultiple
---

# IoWMIQuerySingleInstanceMultiple function


## -description

The <b>IoWMIQuerySingleInstanceMultiple</b> routine returns all WMI data block instances that implement the specified WMI classes with the specified instance names.

## -parameters

### -param DataBlockObjectList 

[in]
Pointer to an array of pointers of WMI data block objects. The caller opens a data block object for each WMI class with the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmiopenblock">IoWMIOpenBlock</a> routine. Each object must be opened with the WMIGUID_QUERY access right.

### -param InstanceNames 

[in]
Pointer to an array of <a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structures containing instance names. The <i>n</i>th instance name in the array corresponds to the value of the <b>InstanceName</b> property for the <i>n</i>th WMI class specified in the array pointed to by the <i>DataBlockObjectList</i> parameter.

### -param ObjectCount 

[in]
Specifies the number of entries in the arrays passed in the <i>DataBlockObjectList</i> and <i>InstanceNames</i> parameters.

### -param InOutBufferSize 

[in, out]
Pointer to a memory location that specifies the size of the buffer passed in the <i>OutBuffer</i> parameter. If the routine succeeds, it updates the memory location to specify the number of bytes actually stored in <i>OutBuffer</i>. If the routine fails with STATUS_BUFFER_TOO_SMALL, it returns the number of bytes required to return the data.

### -param OutBuffer 

[out, optional]
Pointer to the buffer where the routine returns the WMI data. The routine returns a sequence of variable-sized <a href="/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_single_instance">WNODE_SINGLE_INSTANCE</a> structures, one for each data block instance. The <b>WnodeHeader.Linkage</b> member of each <b>WNODE_SINGLE_INSTANCE</b> structure contains the offset from the beginning of the current <b>WNODE_SINGLE_INSTANCE</b> to the beginning of the next <b>WNODE_SINGLE_INSTANCE</b>. The final block in the chain has <b>WnodeHeader.Linkage</b> set to zero. Each distinct data block instance corresponds to a single matching WMI class and instance name. <i>OutBuffer</i> must point to a buffer allocated from nonpaged pool.

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
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer passed by the caller in the <i>OutBuffer</i> parameter is too small. The routine returns the required buffer size in the memory location pointed to by the <i>InOutBufferSize</i> parameter.

</td>
</tr>
</table>

## -remarks

<b>IoWMIQuerySingleInstanceMultiple</b> determines which drivers might support the specified WMI classes and instance names, and issues an <a href="/windows-hardware/drivers/kernel/irp-mn-query-single-instance">IRP_MN_QUERY_SINGLE_INSTANCE</a> request to each such driver. Each driver that exports the data block instance with matching <b>InstanceName</b> property returns the appropriate data.

If no drivers implement any of the specified WMI classes and instance names, the routine returns STATUS_SUCCESS. It also returns a value of zero in the memory location pointed to by the <i>InOutBufferSize</i> parameter.

To query for a single WMI class and instance name, use the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmiquerysingleinstance">IoWMIQuerySingleInstance</a> routine. Drivers can use the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmisetsingleinstance">IoWMISetSingleInstance</a> routine to update a class instance.

## -see-also

<a href="/windows-hardware/drivers/kernel/irp-mn-query-single-instance">IRP_MN_QUERY_SINGLE_INSTANCE</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmiopenblock">IoWMIOpenBlock</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmiquerysingleinstance">IoWMIQuerySingleInstance</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmisetsingleinstance">IoWMISetSingleInstance</a>



<a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>