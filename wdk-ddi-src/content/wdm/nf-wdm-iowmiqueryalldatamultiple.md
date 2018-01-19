---
UID: NF:wdm.IoWMIQueryAllDataMultiple
title: IoWMIQueryAllDataMultiple function
author: windows-driver-content
description: The IoWMIQueryAllDataMultiple routine returns all WMI data blocks that implement one of a set of WMI classes.
old-location: kernel\iowmiqueryalldatamultiple.htm
old-project: kernel
ms.assetid: 660ed1ad-3aad-44a9-9523-e167f84fe9d5
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoWMIQueryAllDataMultiple
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoWMIQueryAllDataMultiple
req.alt-loc: NtosKrnl.exe
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoWMIQueryAllDataMultiple function



## -description
The <b>IoWMIQueryAllDataMultiple</b> routine returns all WMI data blocks that implement one of a set of WMI classes.



## -syntax

````
NTSTATUS IoWMIQueryAllDataMultiple(
  _In_      PVOID *DataBlockObjectList,
  _In_      ULONG ObjectCount,
  _Inout_   ULONG *InOutBufferSize,
  _Out_opt_ PVOID OutBuffer
);
````


## -parameters

### -param DataBlockObjectList [in]

Pointer to an array of pointers to WMI data block objects. The caller opens a data block object for each WMI class with the <a href="..\wdm\nf-wdm-iowmiopenblock.md">IoWMIOpenBlock</a> routine. Each object must be opened with the WMIGUID_QUERY access right.


### -param ObjectCount [in]

Specifies the number of entries in the array passed in the <i>DataBlockObjectList</i> parameter.


### -param InOutBufferSize [in, out]

Pointer to a memory location that specifies the size of the buffer passed in the <i>OutBuffer</i> parameter. If the routine succeeds, it updates the memory location to specify the number of bytes actually stored in <i>OutBuffer</i>. If the routine fails with status code of STATUS_BUFFER_TOO_SMALL, it returns the number of bytes required to return the data.


### -param OutBuffer [out, optional]

Pointer to the buffer where the routine returns the WMI data. The routine returns a sequence of variable-sized <a href="..\wmistr\ns-wmistr-tagwnode_all_data.md">WNODE_ALL_DATA</a> structures, one for each set of returned data blocks. The <b>WnodeHeader.Linkage</b> member of each <b>WNODE_ALL_DATA</b> structure contains the offset from the beginning of the current <b>WNODE_ALL_DATA</b> to the beginning of the next <b>WNODE_ALL_DATA</b>. The final block in the chain has <b>WnodeHeader.Linkage</b> set to zero. <i>OutBuffer</i> must point to a buffer allocated from nonpaged pool. 


## -returns
The routine returns an NTSTATUS code. Possible return values include:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The operation succeeded. The routine returns the WMI data in the buffer pointed to by the <i>OutBuffer</i> parameter. The routine also returns the size, in bytes, of the returned data in the memory location pointed to by the <i>InOutBufferSize</i> parameter.
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>The buffer passed by the caller in the <i>OutBuffer</i> parameter is too small. The routine returns the required buffer size in the memory location pointed to by the <i>InOutBufferSize</i> parameter. 

 


## -remarks
<b>IoWMIQueryAllDataMultiple</b> determines which drivers support the specified WMI classes, and issues an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551650">IRP_MN_QUERY_ALL_DATA</a> request to every such driver. 

If no drivers implement any of the specified WMI classes, the routine returns STATUS_SUCCESS It also returns a value of zero in the memory location pointed to by the <i>InOutBufferSize</i> parameter.

To query a single WMI class, use <a href="..\wdm\nf-wdm-iowmiqueryalldata.md">IoWMIQueryAllData</a>. 


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-iowmiopenblock.md">IoWMIOpenBlock</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iowmiqueryalldata.md">IoWMIQueryAllData</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551650">IRP_MN_QUERY_ALL_DATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoWMIQueryAllDataMultiple routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

