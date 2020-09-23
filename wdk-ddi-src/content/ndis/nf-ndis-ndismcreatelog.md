---
UID: NF:ndis.NdisMCreateLog
title: NdisMCreateLog function (ndis.h)
description: NdisMCreateLog allocates and opens a log file in which a miniport driver can write data to be displayed by a driver-dedicated Win32 application.
old-location: netvista\ndismcreatelog.htm
tech.root: netvista
ms.assetid: 804112cf-fc59-4a04-b848-4239b32e35d7
ms.date: 05/02/2018
keywords: ["NdisMCreateLog function"]
ms.keywords: NdisMCreateLog, NdisMCreateLog function [Network Drivers Starting with Windows Vista], miniport_logging_ref_e6ca8197-b4f0-4eb9-bfe4-f4b957a124c8.xml, ndis/NdisMCreateLog, netvista.ndismcreatelog
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCreateLog (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCreateLog (NDIS 5.1)) in   Windows XP.
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisMCreateLog
 - ndis/NdisMCreateLog
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisMCreateLog
---

# NdisMCreateLog function


## -description

<b>NdisMCreateLog</b> allocates and opens a log file in which a miniport driver can write data to be
  displayed by a driver-dedicated Win32 application.

## -parameters

### -param MiniportAdapterHandle 

[in]
Specifies the handle input to 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>.

### -param Size 

[in]
Specifies how many bytes to allocate for the log file. NDIS creates a temporary file that is not
     stored on disk.

### -param LogHandle 

[out]
Pointer to a caller-supplied variable in which this function returns a handle to the log file.
     This handle is a required parameter to the 
     <b>Ndis</b><i>Xxx</i><b>Log</b> functions that the miniport driver calls subsequently.

## -returns

<b>NdisMCreateLog</b> can return one of the following:

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
The miniport driver can use the handle returned at 
       <i>LogHandle</i> to write data to the NDIS-allocated log file.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A log file of the specified size could not be allocated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
The driver already called 
       <b>NdisMCreateLog</b> successfully.

</td>
</tr>
</table>

## -remarks

A miniport driver can call the 
    <b>NdisM..Log</b> functions to provide any information the driver writer chooses. Whatever the miniport
    driver logs can be displayed by a driver-dedicated Win32 application. Such an application calls the Win32
    function 
    <a href="/windows/win32/api/ioapiset/nf-ioapiset-deviceiocontrol">DeviceIoControl</a> with IOCTL_NDIS_GET_LOG_DATA periodically to retrieve whatever the miniport driver
    has written to the log file. For example, an under-development miniport driver might write test data to
    be displayed by its corresponding application.

If 
    <b>NdisMCreateLog</b> returns NDIS_STATUS_RESOURCES, the driver can adjust the original 
    <i>Size</i> down and try calling this function again. However, a miniport driver cannot call 
    <b>NdisMCreateLog</b> to create more than one log file after a call succeeds.

Whatever size of log file is allocated, subsequent calls to 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismwritelogdata">NdisMWriteLogData</a> store data in this
    file, which is treated as a circular buffer. That is, a sequence of calls to 
    <b>NdisMWriteLogData</b> eventually overwrites the data originally written to the log file.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcloselog">NdisMCloseLog</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismflushlog">NdisMFlushLog</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismwritelogdata">NdisMWriteLogData</a>