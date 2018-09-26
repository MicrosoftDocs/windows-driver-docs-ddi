---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_CREATE_GPADL_FROM_MDL
title: FN_VMB_CHANNEL_CREATE_GPADL_FROM_MDL
author: windows-driver-content
description: The VmbChannelCreateGpadlFromMdl function creates a Guest Physical Address Descriptor List (GPADL) that describes a client-side buffer. The GPADL can be used in the server to access the buffer.
tech.root: netvista
ms.assetid: 910ee2ef-69af-448c-b911-b9cfe782eb74
ms.author: windowsdriverdev
ms.date: 05/21/2018
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: vmbuskernelmodeclientlibapi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	vmbuskernelmodeclientlibapi.h
api_name: 
-	FN_VMB_CHANNEL_CREATE_GPADL_FROM_MDL
product:
-	Windows
targetos: Windows
---

# FN_VMB_CHANNEL_CREATE_GPADL_FROM_MDL callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelCreateGpadlFromMdl</b> function creates a Guest Physical Address Descriptor List (GPADL) that describes a client-side buffer. The GPADL can be used
in the server to access the buffer.  

## -prototype

```
//Declaration

FN_VMB_CHANNEL_CREATE_GPADL_FROM_MDL FnVmbChannelCreateGpadlFromMdl; 

// Definition

NTSTATUS FnVmbChannelCreateGpadlFromMdl 
(
	VMBCHANNEL Channel
	UINT32 Flags
	PMDL Mdl
	UINT32 StartOffsetWithinMdl
	UINT32 DataLengthWithinMdl
	PUINT32 GpadlHandle
)
{...}

```

## -parameters

### -param Channel

A handle for a channel. 

### -param Flags

Flags. The possible values are the following:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="VMBUS_CHANNEL_GPADL_READ_ONLY"></a><a id="vmbus_channel_gpadl_read_only"></a><dl>
<dt><b>VMBUS_CHANNEL_GPADL_READ_ONLY</b></dt>
</dl>
</td>
<td width="60%">
If you specify this value, the buffer is read-only. Otherwise, the server can write to the buffer. This is not a security measure, but can improve snapshot and live migration performance.

</td>
</tr>
</table>

### -param Mdl

A pointer to a Memory Descriptor List (MDL) chain that describes the buffer. The buffer may
have multiple pieces, which are chained by using the MDL next pointer.

### -param StartOffsetWithinMdl

An offset, in bytes, in the MDL at which to start the mapping.

### -param DataLengthWithinMdl

The length, in bytes, of the buffer chain. If this value is zero (0),
use until the end of the MDL.

### -param GpadlHandle

The GPADL handle of the created MDL. Send this to the server to use with the <a href="https://msdn.microsoft.com/A7801EE9-BFDB-4F77-9DA4-A6612F63AD48">VmbChannelMapGpadl</a> function.

## -returns

Returns STATUS_SUCCESS if the operation succeeds, or an appropriate NTSTATUS error code otherwise.

## -remarks

When this function returns, the server
endpoint can call <a href="https://msdn.microsoft.com/A7801EE9-BFDB-4F77-9DA4-A6612F63AD48">VmbChannelMapGpadl</a>, because VMBus will already have send
the GPADL description to the opposite endpoint and received confirmation.

 The GPADL must be deleted by using the <a href="https://msdn.microsoft.com/B1446A29-F2C1-4F08-8B38-5BE9188F5132">VmbChannelDeleteGpadl</a> function.

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. 
>
> To access the KMCL interface, allocate a **KMCL_CLIENT_INTERFACE_V1** structure to receive the interface, then call either [**WdfFdoQueryForInterface**](../wdffdo/nf-wdffdo-wdffdoqueryforinterface.md) or [**WdfIoTargetQueryForInterface**](../wdfiotarget/nf-wdfiotarget-wdfiotargetqueryforinterface.md) with these parameters:
> 
> - *InterfaceType* parameter: **KMCL_CLIENT_INTERFACE_TYPE**
> - *Size* parameter: `sizeof(KMCL_CLIENT_INTERFACE_V1)`
> - *Version* parameter: **KMCL_CLIENT_INTERFACE_VERSION_LATEST** 
>
> If the interface query function succeeds, the **KMCL_CLIENT_INTERFACE_V1** structure contains function pointers for the VMBus KMCL functions that you can use to call them.
>
> For more information about driver-defined interfaces, see [Using Driver-Defined Interfaces](https://docs.microsoft.com/windows-hardware/drivers/wdf/using-driver-defined-interfaces).

## -see-also

<a href="https://msdn.microsoft.com/B1446A29-F2C1-4F08-8B38-5BE9188F5132">VmbChannelDeleteGpadl</a>



<a href="https://msdn.microsoft.com/A7801EE9-BFDB-4F77-9DA4-A6612F63AD48">VmbChannelMapGpadl</a>
