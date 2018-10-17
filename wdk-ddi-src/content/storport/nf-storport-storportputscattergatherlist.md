---
UID: NF:storport.StorPortPutScatterGatherList
title: StorPortPutScatterGatherList function
author: windows-driver-content
description: The StorPortPutScatterGatherList routine releases any resources associated with a scatter/gather list that was previously created by a call to the StorPortBuildScatterGatherList routine.
old-location: storage\storportputscattergatherlist.htm
tech.root: storage
ms.assetid: 0b380597-09dc-414f-b2c6-f541d35540da
ms.date: 3/29/2018
ms.keywords: StorPortPutScatterGatherList, StorPortPutScatterGatherList routine [Storage Devices], storage.storportputscattergatherlist, storport/StorPortPutScatterGatherList, storprt_d8e74add-b512-4584-aa56-d9337ad3d7a9.xml
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: StorPortIrql
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	storport.h
api_name:
-	StorPortPutScatterGatherList
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortPutScatterGatherList function


## -description


The <b>StorPortPutScatterGatherList</b> routine releases any resources associated with a scatter/gather list that was previously created by a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567038">StorPortBuildScatterGatherList</a> routine.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param ScatterGatherList [in]

A pointer to a buffer that contains a scatter/gather list that was previously created by a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567038">StorPortBuildScatterGatherList</a> routine.


### -param WriteToDevice [in]

A value that indicates the direction of the DMA transfer that has completed. A value of <b>TRUE</b> indicates a transfer from the data buffer to the device, and <b>FALSE</b> indicates a transfer from the device to the data buffer.


## -returns



<b>StorPortPutScatterGatherList</b> returns one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This function is not implemented on the active operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the routine released the scatter/gather list successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>HwDeviceExtension</i> that was passed was <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_IRQL</b></dt>
</dl>
</td>
<td width="60%">
The call was made at an invalid IRQL.

</td>
</tr>
</table>
 




## -remarks



The <b>StorPortPutScatterGatherList</b> routine does not free the buffer memory for the scatter/gather list, because the miniport driver allocated this memory. 

After the <b>StorPortPutScatterGatherList</b> routine returns, the miniport driver can reuse the buffer to create a new scatter/gather list by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567038">StorPortBuildScatterGatherList</a> again. If a miniport driver has finished using the buffer for the scatter/gather list, it should free the memory for the buffer after the <b>StorPortPutScatterGatherList</b> routine returns. If the miniport driver allocates the buffer memory with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567031">StorPortAllocatePool</a> routine, it should free the memory by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567065">StorPortFreePool</a> routine.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567038">StorPortBuildScatterGatherList</a>
 

 

