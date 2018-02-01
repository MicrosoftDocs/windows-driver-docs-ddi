---
UID: NF:storport.StorPortBuildScatterGatherList
title: StorPortBuildScatterGatherList function
author: windows-driver-content
description: The StorPortBuildScatterGatherList routine creates a scatter/gather list for the specified data buffer.
old-location: storage\storportbuildscattergatherlist.htm
old-project: storage
ms.assetid: cdea67aa-14fa-45c1-8af0-8db48042b1b2
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storport/StorPortBuildScatterGatherList, StorPortBuildScatterGatherList, storprt_ed0a920c-d8f4-44f2-a262-5a74470ec67a.xml, StorPortBuildScatterGatherList routine [Storage Devices], storage.storportbuildscattergatherlist
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
req.ddi-compliance: 
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
-	StorPortBuildScatterGatherList
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortBuildScatterGatherList function


## -description


The <b>StorPortBuildScatterGatherList</b> routine creates a scatter/gather list for the specified data buffer.


## -syntax


````
ULONG StorPortBuildScatterGatherList(
  _In_    PVOID                        HwDeviceExtension,
  _In_    PVOID                        Mdl,
  _In_    PVOID                        CurrentVa,
  _In_    ULONG                        Length,
  _In_    PPOST_SCATTER_GATHER_EXECUTE ExecutionRoutine,
  _In_    PVOID                        Context,
  _In_    BOOLEAN                      WriteToDevice,
  _Inout_ PVOID                        ScatterGatherBuffer,
  _In_    ULONG                        ScatterGatherBufferLength
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Mdl [in]

A pointer to a memory descriptor list (MDL) that describes the memory pages associated with the data buffer.


### -param CurrentVa [in]

The virtual address of the data buffer.


### -param Length [in]

The length, in bytes, of the data buffer.


### -param ExecutionRoutine [in]

A pointer to a miniport driver-supplied <i>ExecutionRoutine</i>. The Storport driver calls this routine after creating the scatter/gather list. The miniport driver should perform all operations that make use of the scatter/gather list inside the execution routine, not in the code that follows the call to the <b>StorPortBuildScatterGatherList</b> routine.

An <i>ExecutionRoutine</i> is declared as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
ExecutionRoutine (
    IN PVOID  *DeviceObject,
    IN PVOID  *Irp,
    IN PSTOR_SCATTER_GATHER_LIST  ScatterGather,
    IN PVOID  Context
    );</pre>
</td>
</tr>
</table></span></div>

The Storport driver calls a miniport driver's <i>ExecutionRoutine</i> at IRQL = DISPATCH_LEVEL.


#### Context

The context value specified in the <b>StorPortBuildScatterGatherList</b> function's <i>Context</i> parameter.


#### DeviceObject

Miniport drivers should ignore this parameter.


#### Irp

Miniport drivers should ignore this parameter.


#### ScatterGather

A pointer to a <a href="..\storport\ns-storport-_stor_scatter_gather_list.md">STOR_SCATTER_GATHER_LIST</a> structure that contains the scatter/gather list for the specified data buffer.


### -param Context [in]

A context value that the port driver passes to the execution routine specified in the <i>ExecutionRoutine</i> parameter. The execution routine uses this value to uniquely identify the request.


### -param WriteToDevice [in]

A value that indicates the direction of the DMA transfer. A value of <b>TRUE</b> indicates a transfer that is from the data buffer to the device, and a value of <b>FALSE</b> indicates a transfer that is from the device to the data buffer.


### -param ScatterGatherBuffer [in, out]

A pointer to a miniport-supplied buffer that receives the scatter/gather list. A miniport driver can allocate memory for this buffer by calling the <a href="..\storport\nf-storport-storportallocatepool.md">StorPortAllocatePool</a> routine.


### -param ScatterGatherBufferLength [in]

The size, in bytes, of the buffer pointed to by the <i>ScatterGatherBuffer</i> parameter.


## -returns


<b>StorPortBuildScatterGatherList</b> returns one of the following values:
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
Indicates that the routine created the scatter/gather list successfully.

<div class="alert"><b>Important</b>  See 'Remarks'.</div>
<div> </div>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>HwDeviceExtension</i> passed was <b>NULL</b>.

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
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The system has insufficient map registers available for the transfer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_BUFFER_TOO_SMALL </b></dt>
</dl>
</td>
<td width="60%">
The Length parameter is too big to fit within the buffer.

</td>
</tr>
</table> 



## -remarks


The miniport driver calls <a href="..\storport\nf-storport-storportputscattergatherlist.md">StorPortPutScatterGatherList</a> to release the resources that <b>StorPortBuildScatterGatherList</b> allocated while constructing the scatter/gather list. 

The miniport driver must call <a href="..\storport\nf-storport-storportputscattergatherlist.md">StorPortPutScatterGatherList</a> before freeing or reusing the memory it allocated for the scatter/gather list.
<div class="alert"><b>Note</b>  If <b>StorPortBuildScatterGatherList</b> returns STOR_STATUS_SUCCESS, then the callback in <i>ExecutionRoutine</i> was successfully queued to execute after the scatter/gather list is created. The miniport must not assume that <i>ExecutionRoutine</i> was called or that the scatter/gather list is ready when <b>StorPortBuildScatterGatherList</b> returns.   If necessary, the miniport can synchronize the execution of code following <b>StorPortBuildScatterGatherList</b> with the callback in <i>ExecutionRoutine</i> to ensure that the scatter/gather list is available.</div><div> </div>


## -see-also

<a href="..\storport\nf-storport-storportallocatepool.md">StorPortAllocatePool</a>

<a href="..\storport\ns-storport-_stor_scatter_gather_list.md">STOR_SCATTER_GATHER_LIST</a>

<a href="..\storport\nf-storport-storportputscattergatherlist.md">StorPortPutScatterGatherList</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortBuildScatterGatherList routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

