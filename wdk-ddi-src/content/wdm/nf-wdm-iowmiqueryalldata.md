---
UID: NF:wdm.IoWMIQueryAllData
title: IoWMIQueryAllData function
author: windows-driver-content
description: The IoWMIQueryAllData routine returns all WMI data blocks that implement a given WMI class.
old-location: kernel\iowmiqueryalldata.htm
old-project: kernel
ms.assetid: d0efae7b-5a53-4f8a-b2d7-c30eefad7c90
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k104_120c73d7-392a-4604-8f6b-11c4e717fcac.xml, wdm/IoWMIQueryAllData, IoWMIQueryAllData, kernel.iowmiqueryalldata, IoWMIQueryAllData routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later versions of the Windows operating system.
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	IoWMIQueryAllData
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoWMIQueryAllData function


## -description


The <b>IoWMIQueryAllData</b> routine returns all WMI data blocks that implement a given WMI class.


## -syntax


````
NTSTATUS IoWMIQueryAllData(
  _In_      PVOID DataBlockObject,
  _Inout_   ULONG *InOutBufferSize,
  _Out_opt_ PVOID OutBuffer
);
````


## -parameters




### -param DataBlockObject [in]

Pointer to a WMI data block object. The caller opens the data block object for the WMI class with the <a href="..\wdm\nf-wdm-iowmiopenblock.md">IoWMIOpenBlock</a> routine. The object must be opened with the WMIGUID_QUERY access right. 


### -param InOutBufferSize [in, out]

Pointer to a memory location that specifies the size of the buffer passed in the <i>OutBuffer</i> parameter. If the routine succeeds, it updates the memory location to specify the number of bytes actually stored in <i>OutBuffer</i>. If the routine fails with status code of STATUS_BUFFER_TOO_SMALL, it returns the number of bytes required to return the data.


### -param OutBuffer [out, optional]

Pointer to the buffer where the routine returns the WMI data. The routine returns a sequence of variable-sized <a href="..\wmistr\ns-wmistr-tagwnode_all_data.md">WNODE_ALL_DATA</a> structures, one for each set of returned data blocks. The <b>WnodeHeader.Linkage</b> member of each <b>WNODE_ALL_DATA</b> structure contains the offset from the beginning of the current <b>WNODE_ALL_DATA</b> to the beginning of the next <b>WNODE_ALL_DATA</b>. The final block in the chain has <b>WnodeHeader.Linkage</b> set to zero. <i>OutBuffer</i> must point to a buffer allocated from nonpaged pool. 


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
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer passed by the caller in the <i>OutBuffer</i> parameter is too small. The routine returns the required buffer size in the memory location pointed to by the <i>InOutBufferSize</i> parameter. 

</td>
</tr>
</table> 



## -remarks


<b>IoWMIQueryAllData</b> determines which drivers support the specified WMI class, and issues an <b>IRP_MN_QUERY_ALL_DATA</b> request to every such driver.

To query for multiple WMI classes, use <a href="..\wdm\nf-wdm-iowmiqueryalldatamultiple.md">IoWMIQueryAllDataMultiple</a>.



## -see-also

<a href="..\wdm\nf-wdm-iowmiqueryalldatamultiple.md">IoWMIQueryAllDataMultiple</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551650">IRP_MN_QUERY_ALL_DATA</a>

<a href="..\wdm\nf-wdm-iowmiopenblock.md">IoWMIOpenBlock</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoWMIQueryAllData routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

