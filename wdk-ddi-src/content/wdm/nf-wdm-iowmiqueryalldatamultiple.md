---
UID: NF:wdm.IoWMIQueryAllDataMultiple
title: IoWMIQueryAllDataMultiple function (wdm.h)
description: The IoWMIQueryAllDataMultiple routine returns all WMI data blocks that implement one of a set of WMI classes.
old-location: kernel\iowmiqueryalldatamultiple.htm
tech.root: kernel
ms.assetid: 660ed1ad-3aad-44a9-9523-e167f84fe9d5
ms.date: 04/30/2018
keywords: ["IoWMIQueryAllDataMultiple function"]
ms.keywords: IoWMIQueryAllDataMultiple, IoWMIQueryAllDataMultiple routine [Kernel-Mode Driver Architecture], k104_6431ed7a-35b6-4c48-8477-390c4c31220c.xml, kernel.iowmiqueryalldatamultiple, wdm/IoWMIQueryAllDataMultiple
f1_keywords:
 - "wdm/IoWMIQueryAllDataMultiple"
 - "IoWMIQueryAllDataMultiple"
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
- IoWMIQueryAllDataMultiple
targetos: Windows
req.typenames: 
---

# IoWMIQueryAllDataMultiple function


## -description


The <b>IoWMIQueryAllDataMultiple</b> routine returns all WMI data blocks that implement one of a set of WMI classes.


## -parameters




### -param DataBlockObjectList [in]

Pointer to an array of pointers to WMI data block objects. The caller opens a data block object for each WMI class with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmiopenblock">IoWMIOpenBlock</a> routine. Each object must be opened with the WMIGUID_QUERY access right.


### -param ObjectCount [in]

Specifies the number of entries in the array passed in the <i>DataBlockObjectList</i> parameter.


### -param InOutBufferSize [in, out]

Pointer to a memory location that specifies the size of the buffer passed in the <i>OutBuffer</i> parameter. If the routine succeeds, it updates the memory location to specify the number of bytes actually stored in <i>OutBuffer</i>. If the routine fails with status code of STATUS_BUFFER_TOO_SMALL, it returns the number of bytes required to return the data.


### -param OutBuffer [out, optional]

Pointer to the buffer where the routine returns the WMI data. The routine returns a sequence of variable-sized <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_all_data">WNODE_ALL_DATA</a> structures, one for each set of returned data blocks. The <b>WnodeHeader.Linkage</b> member of each <b>WNODE_ALL_DATA</b> structure contains the offset from the beginning of the current <b>WNODE_ALL_DATA</b> to the beginning of the next <b>WNODE_ALL_DATA</b>. The final block in the chain has <b>WnodeHeader.Linkage</b> set to zero. <i>OutBuffer</i> must point to a buffer allocated from nonpaged pool. 


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



<b>IoWMIQueryAllDataMultiple</b> determines which drivers support the specified WMI classes, and issues an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-all-data">IRP_MN_QUERY_ALL_DATA</a> request to every such driver. 

If no drivers implement any of the specified WMI classes, the routine returns STATUS_SUCCESS It also returns a value of zero in the memory location pointed to by the <i>InOutBufferSize</i> parameter.

To query a single WMI class, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmiqueryalldata">IoWMIQueryAllData</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-all-data">IRP_MN_QUERY_ALL_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmiopenblock">IoWMIOpenBlock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmiqueryalldata">IoWMIQueryAllData</a>
 

 

