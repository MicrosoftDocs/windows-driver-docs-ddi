---
UID: NF:ndis.NdisMMapIoSpace
title: NdisMMapIoSpace function
author: windows-driver-content
description: NdisMMapIoSpace maps a given bus-relative &#0034;physical&#0034; range of device RAM or registers onto a system-space virtual range.
old-location: netvista\ndismmapiospace.htm
old-project: netvista
ms.assetid: 16c62146-ed8d-4bf7-9d5e-0c5dbbf3c9c4
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisMMapIoSpace
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMMapIoSpace (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMMapIoSpace (NDIS 5.1)) in   Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMMapIoSpace
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Miniport_Driver_Function, NdisMMapIoSpace
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMMapIoSpace function



## -description
<b>NdisMMapIoSpace</b> maps a given bus-relative "physical" range of device RAM or registers onto a
  system-space virtual range.



## -syntax

````
NDIS_STATUS NdisMMapIoSpace(
  _Out_ PVOID                 *VirtualAddress,
  _In_  NDIS_HANDLE           MiniportAdapterHandle,
  _In_  NDIS_PHYSICAL_ADDRESS PhysicalAddress,
  _In_  UINT                  Length
);
````


## -parameters

### -param VirtualAddress [out]

Pointer to a caller-supplied variable that is set to the converted virtual address if the call is
     successful.


### -param MiniportAdapterHandle [in]

Specifies the handle input to 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>.


### -param PhysicalAddress [in]

Specifies the bus-relative base physical address of the device memory range to be mapped.


### -param Length [in]

Specifies the number of bytes to be mapped.


## -returns
<b>NdisMMapIoSpace</b> can return any of the following status values:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>The device memory range was mapped successfully so the value at 
       <i>VirtualAddress</i> is valid and the mapped range has been claimed in the registry for the
       NIC.
<dl>
<dt><b>NDIS_STATUS_RESOURCE_CONFLICT</b></dt>
</dl>An attempt to claim the device memory range in the registry has failed, possibly because another
       driver has already claimed the range for its device. 
       <b>NdisMMapIoSpace</b> logs an error if this occurs.
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>The memory could not be mapped or sufficient virtual memory could not be allocated.
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>Either the bus type or bus number is out of range or the given 
       <i>PhysicalAddress</i> and 
       <i>Length</i> were invalid (possibly not within the I/O space of the current platform).

 


## -remarks
This function is called by drivers of NICs that have on-board memory or a bank of device registers
    appearing in the I/O space of the host. For example, the driver of a NIC that uses PIO calls 
    <b>NdisMMapIoSpace</b>.

A successful call to 
    <b>NdisMMapIoSpace</b> claims hardware resources in the registry for the driver's NIC. Consequently, only 
    <i>MiniportInitializeEx</i> functions call 
    <b>NdisMMapIoSpace</b>.

<b>NdisMMapIoSpace</b> sets the variable at 
    <i>VirtualAddress</i> to <b>NULL</b> if it does not return NDIS_STATUS_SUCCESS.

MiniportInitializeEx either gets the 
    <i>PhysicalAddress</i> value from the driver's 
    <b>Parameters</b> registry key or by calling a bus-type-specific 
    <b>Ndis<i>Xxx</i></b> configuration function. The given physical address range must fall within the I/O space of the
    current platform. It is a programming error to call 
    <b>NdisMMapIoSpace</b> with a host physical memory address.


## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismgetbusdata.md">NdisMGetBusData</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismunmapiospace.md">NdisMUnmapIoSpace</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisopenconfigurationex.md">NdisOpenConfigurationEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisreadregisteruchar.md">NdisReadRegisterUchar</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisreadregisterulong.md">NdisReadRegisterUlong</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisreadregisterushort.md">NdisReadRegisterUshort</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiswriteregisteruchar.md">NdisWriteRegisterUchar</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiswriteregisterulong.md">NdisWriteRegisterUlong</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiswriteregisterushort.md">NdisWriteRegisterUshort</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMMapIoSpace function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

