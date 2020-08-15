---
UID: NF:ndis.NdisMWriteLogData
title: NdisMWriteLogData function (ndis.h)
description: NdisMWriteLogData transfers driver-supplied information into the log file for consumption and display by a driver-dedicated Win32 application.
old-location: netvista\ndismwritelogdata.htm
tech.root: netvista
ms.assetid: 38923308-0268-49b3-9f9d-0fa2b62f7533
ms.date: 05/02/2018
keywords: ["NdisMWriteLogData function"]
ms.keywords: NdisMWriteLogData, NdisMWriteLogData function [Network Drivers Starting with Windows Vista], miniport_logging_ref_ca57cae5-4951-4c02-a745-d668bc8ec663.xml, ndis/NdisMWriteLogData, netvista.ndismwritelogdata
f1_keywords:
 - "ndis/NdisMWriteLogData"
 - "NdisMWriteLogData"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMWriteLogData (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMWriteLogData (NDIS 5.1)) in   Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miniport_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisMWriteLogData
targetos: Windows
req.typenames: 
---

# NdisMWriteLogData function


## -description


<b>NdisMWriteLogData</b> transfers driver-supplied information into the log file for consumption and display
  by a driver-dedicated Win32 application.


## -parameters




### -param LogHandle 
[in]
Specifies the handle returned by 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcreatelog">NdisMCreateLog</a>.


### -param LogBuffer 
[in]
Pointer to a driver-allocated buffer containing the information to be written.


### -param LogBufferSize 
[in]
Specifies how many bytes of data to copy into the log file.


## -returns



<b>NdisMWriteLogData</b> can return one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The driver-supplied data at 
       <i>LogBuffer</i> has been copied into the log file.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The given 
       <i>LogBufferSize</i> is too large, that is, larger than the log file itself.

</td>
</tr>
</table>
 




## -remarks



If the driver-dedicated application has an outstanding request for log file data, 
    <b>NdisMWriteLogData</b> satisfies that request as soon as it has copied the driver-supplied information
    into the log file.

The miniport driver can supply a 
    <i>LogBuffer</i> pointer to a location on the kernel stack if it is currently running at IRQL <
    DISPATCH_LEVEL. Otherwise, 
    <i>LogBuffer</i> must access a buffer that the driver allocated from nonpaged pool.

The driver must release any spin lock it is holding before calling 
    <b>NdisMWriteLogData</b>.

<b>NdisMWriteLogData</b> does not recognize boundaries between log records, nor does the Win32 function, 
    <a href="https://docs.microsoft.com/windows/desktop/api/ioapiset/nf-ioapiset-deviceiocontrol">DeviceIoControl</a>, which applications can call with IOCTL_NDIS_GET_LOG_DATA to retrieve data written
    to an NDIS log file by an NDIS miniport driver. 
    <b>NdisMWriteLogData</b> writes all miniport driver-supplied data at 
    <i>LogBuffer</i> into the log file as a byte stream. 
    <b>DeviceIoControl</b> reads the data from such a log as a byte stream, as well.

Consequently, an application reading an NDIS log must collect retrieved data into records. To aid such
    an application in collecting variable-length records, any miniport driver writing to such a log can
    insert a marker at the beginning of each record. Then, the application formatting the retrieved data can
    search for these markers to determine the start of each record.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatefromnpagedlookasidelist">
   NdisAllocateFromNPagedLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatememorywithtagpriority">
   NdisAllocateMemoryWithTagPriority</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcloselog">NdisMCloseLog</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcreatelog">NdisMCreateLog</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismflushlog">NdisMFlushLog</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreleasespinlock">NdisReleaseSpinLock</a>
 

 

