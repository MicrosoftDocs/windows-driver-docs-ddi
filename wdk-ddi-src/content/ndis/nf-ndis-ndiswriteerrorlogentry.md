---
UID: NF:ndis.NdisWriteErrorLogEntry
title: NdisWriteErrorLogEntry function (ndis.h)
description: NdisWriteErrorLogEntry writes an entry to the system I/O error log file.
old-location: netvista\ndiswriteerrorlogentry.htm
tech.root: netvista
ms.assetid: d36174ef-4df2-49ec-9167-cfb150f090f8
ms.date: 05/02/2018
ms.keywords: NdisWriteErrorLogEntry, NdisWriteErrorLogEntry function [Network Drivers Starting with Windows Vista], miniport_logging_ref_754f8e03-f922-4e6d-b2ef-20fb8027b645.xml, ndis/NdisWriteErrorLogEntry, netvista.ndiswriteerrorlogentry
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisWriteErrorLogEntry (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisWriteErrorLogEntry (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisWriteErrorLogEntry
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisWriteErrorLogEntry function


## -description


<b>NdisWriteErrorLogEntry</b> writes an entry to the system I/O error log file.


## -parameters




### -param NdisAdapterHandle [in]

Specifies the handle representing the NIC that is the cause of the I/O error to be logged. This
     handle is an input parameter to 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>.


### -param ErrorCode [in]

Specifies the NDIS_ERRROR_CODE_<i>XXX</i> code that best describes the I/O error as one of the following values:
     





#### NDIS_ERROR_CODE_RESOURCE_CONFLICT

The driver could not access a required resource.



#### NDIS_ERROR_CODE_OUT_OF_RESOURCES

The hardware or driver ran out of resources.



#### NDIS_ERROR_CODE_HARDWARE_FAILURE

The driver detected a hardware error.



#### NDIS_ERROR_CODE_ADAPTER_NOT_FOUND

The network adapter was not found.



#### NDIS_ERROR_CODE_INTERRUPT_CONNECT

The interrupt registration failed.



#### NDIS_ERROR_CODE_DRIVER_FAILURE

A driver failure occurred that does not match any of the other error conditions.



#### NDIS_ERROR_CODE_BAD_VERSION

The driver detected a version mismatch.



#### NDIS_ERROR_CODE_TIMEOUT

A timeout expired.



#### NDIS_ERROR_CODE_NETWORK_ADDRESS

A network address is invalid.



#### NDIS_ERROR_CODE_UNSUPPORTED_CONFIGURATION

The requested driver configuration is not supported.



#### NDIS_ERROR_CODE_INVALID_VALUE_FROM_ADAPTER

The network adapter hardware provided an invalid value.



#### NDIS_ERROR_CODE_MISSING_CONFIGURATION_PARAMETER

A driver configuration parameter is missing in the registry.



#### NDIS_ERROR_CODE_BAD_IO_BASE_ADDRESS

The I/O base address for the network adapter hardware is invalid.



#### NDIS_ERROR_CODE_RECEIVE_SPACE_SMALL

The amount of receive buffer memory that is available is too small to receive data.



#### NDIS_ERROR_CODE_ADAPTER_DISABLED

The network adapter hardware is disabled.


### -param NumberOfErrorValues [in]

Specifies the number of ULONG values to follow this parameter.


### -param param

<p>Specifies a variable-sized array of ULONGs associated with the error to be logged.</p>




####### - ...

Specifies a variable-sized array of ULONGs associated with the error to be logged.


## -returns



None




## -remarks



<b>NdisWriteErrorLogEntry</b> allocates an I/O error log record, fills in the record with the supplied
    information about the error, and then writes the record to the I/O error log file.

The system places a limit on the potential size of an error log record. For Windows 2000 and later
    versions, the limit is defined as ERROR_LOG_MAXIMUM_SIZE. The 
    <i>NumberOfErrorValues</i> passed to 
    <b>NdisWriteErrorLogEntry</b> therefore has a system-enforced limit, which is considerably less than the
    maximum possible value for a ULONG.

In practice, few callers of 
    <b>NdisWriteErrorLogEntry</b> even approach the limit for 
    <i>NumberOfErrorValues</i> because supplying many additional NDIS_STATUS_<i>XXX</i> values is not particularly helpful to the user or system administrator who later reads the
    error log, using the Win32 event viewer. Logging an I/O error at every possible opportunity is not
    particularly helpful to users either, so a miniport driver should log only critical I/O errors that can
    help a user or system administrator to debug a network failure for which the NIC is responsible on a
    particular machine or a configuration resource conflict discovered during driver initialization.

In general, a miniport driver calls 
    <b>NdisWriteErrorLogEntry</b> during initialization from its 
    <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> function if
    it cannot initialize a NIC that it controls or cannot allocate the hardware resources it needs to carry
    out I/O operations on a NIC. A miniport driver also can call 
    <b>NdisWriteErrorLogEntry</b> when a device-reset operation fails due to unrecoverable hardware error(s).
    Logging these kinds of I/O errors helps users or system administrators to identify a badly configured NIC
    or a NIC with failing hardware components.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/15f82163-a1b5-4cef-a53e-8a97adb2cd92">MiniportResetEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563672">NdisMSetMiniportAttributes</a>
 

 

