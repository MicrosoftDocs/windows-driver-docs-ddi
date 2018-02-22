---
UID: NF:storport.StorPortPutScatterGatherList
title: StorPortPutScatterGatherList function
author: windows-driver-content
description: The StorPortPutScatterGatherList routine releases any resources associated with a scatter/gather list that was previously created by a call to the StorPortBuildScatterGatherList routine.
old-location: storage\storportputscattergatherlist.htm
old-project: storage
ms.assetid: 0b380597-09dc-414f-b2c6-f541d35540da
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: StorPortPutScatterGatherList, storprt_d8e74add-b512-4584-aa56-d9337ad3d7a9.xml, StorPortPutScatterGatherList routine [Storage Devices], storage.storportputscattergatherlist, storport/StorPortPutScatterGatherList
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: DISPATCH_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	storport.h
apiname:
-	StorPortPutScatterGatherList
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortPutScatterGatherList function


## -description


The <b>StorPortPutScatterGatherList</b> routine releases any resources associated with a scatter/gather list that was previously created by a call to the <a href="..\storport\nf-storport-storportbuildscattergatherlist.md">StorPortBuildScatterGatherList</a> routine.


## -syntax


````
ULONG StorPortPutScatterGatherList(
  _In_ PVOID                     HwDeviceExtension,
  _In_ PSTOR_SCATTER_GATHER_LIST ScatterGatherList,
  _In_ BOOLEAN                   WriteToDevice
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param ScatterGatherList [in]

A pointer to a buffer that contains a scatter/gather list that was previously created by a call to the <a href="..\storport\nf-storport-storportbuildscattergatherlist.md">StorPortBuildScatterGatherList</a> routine.


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

After the <b>StorPortPutScatterGatherList</b> routine returns, the miniport driver can reuse the buffer to create a new scatter/gather list by calling the <a href="..\storport\nf-storport-storportbuildscattergatherlist.md">StorPortBuildScatterGatherList</a> again. If a miniport driver has finished using the buffer for the scatter/gather list, it should free the memory for the buffer after the <b>StorPortPutScatterGatherList</b> routine returns. If the miniport driver allocates the buffer memory with the <a href="..\storport\nf-storport-storportallocatepool.md">StorPortAllocatePool</a> routine, it should free the memory by calling the <a href="..\storport\nf-storport-storportfreepool.md">StorPortFreePool</a> routine.




## -see-also

<a href="..\storport\nf-storport-storportbuildscattergatherlist.md">StorPortBuildScatterGatherList</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortPutScatterGatherList routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

