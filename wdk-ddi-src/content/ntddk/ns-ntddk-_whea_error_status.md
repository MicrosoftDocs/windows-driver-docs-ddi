---
UID: NS:ntddk._WHEA_ERROR_STATUS
title: "_WHEA_ERROR_STATUS"
author: windows-driver-content
description: The WHEA_ERROR_STATUS union describes generic error codes that are abstracted from the data contained in implementation-specific error registers.
old-location: whea\whea_error_status.htm
old-project: whea
ms.assetid: 5b11112b-e900-4894-a9ce-6895a4fa1956
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWHEA_ERROR_STATUS, PWHEA_ERROR_STATUS, PWHEA_ERROR_STATUS union pointer [WHEA Drivers and Applications], WHEA_ERROR_STATUS, WHEA_ERROR_STATUS union [WHEA Drivers and Applications], _WHEA_ERROR_STATUS, ntddk/PWHEA_ERROR_STATUS, ntddk/WHEA_ERROR_STATUS, whea.whea_error_status, whearef_3dc93951-2c79-4b1e-b5b0-53ede31c6f37.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	WHEA_ERROR_STATUS
product:
- Windows
targetos: Windows
req.typenames: WHEA_ERROR_STATUS, *PWHEA_ERROR_STATUS
---

# _WHEA_ERROR_STATUS structure


## -description


The WHEA_ERROR_STATUS union describes generic error codes that are abstracted from the data contained in implementation-specific error registers.


## -struct-fields




### -field ErrorStatus

A ULONGLONG representation of the contents of the WHEA_ERROR_STATUS union.


### -field DUMMYSTRUCTNAME

 


### -field DUMMYSTRUCTNAME.Reserved1

Reserved for system use.


### -field DUMMYSTRUCTNAME.ErrorType

The type of hardware error that occurred. Possible values are:




### -field DUMMYSTRUCTNAME.Address

A single bit that indicates if the error was detected on the address signals or during the address portion of the transaction.


### -field DUMMYSTRUCTNAME.Control

A single bit that indicates if the error was detected on the control signals or during the control portion of the transaction.


### -field DUMMYSTRUCTNAME.Data

A single bit that indicates if the error was detected on the data signals or during the data portion of the transaction.


### -field DUMMYSTRUCTNAME.Responder

A single bit that indicates that the error was detected by the responder of the transaction.


### -field DUMMYSTRUCTNAME.Requester

A single bit that indicates that the error was detected by the requester of the transaction.


### -field DUMMYSTRUCTNAME.FirstError

A single bit that indicates that the error is the first error to occur if multiple errors are logged for a section type. Setting of this bit is optional.


### -field DUMMYSTRUCTNAME.Overflow

A single bit that indicates that additional errors occurred but were not logged due to an overflow of the logging resources.


### -field DUMMYSTRUCTNAME.Reserved2

Reserved for system use.


##### - ErrorType.ERRTYP_BUS

A bus error.


##### - ErrorType.ERRTYP_CACHE

A cache error.


##### - ErrorType.ERRTYP_FLOW

An overflow or underflow of a queue that is internal to the component.


##### - ErrorType.ERRTYP_FUNCTION

An error in one or more functional units.


##### - ErrorType.ERRTYP_IMPROPER

An improper access error.


##### - ErrorType.ERRTYP_INTERNAL

An error internal to the component.


##### - ErrorType.ERRTYP_LOSSOFLOCKSTEP

A loss of lockstep.


##### - ErrorType.ERRTYP_MAP

The virtual address was not found on IO-TLB or IO-PDIR.


##### - ErrorType.ERRTYP_MEM

A memory error.


##### - ErrorType.ERRTYP_PARITY

A bus parity error.


##### - ErrorType.ERRTYP_PATHERROR

A bus path error.


##### - ErrorType.ERRTYP_POISONED

A read operation was issued to data that has been corrupted.


##### - ErrorType.ERRTYP_PROTOCOL

A bus protocol error.


##### - ErrorType.ERRTYP_RESPONSE

A response was received that was not associated with a request.


##### - ErrorType.ERRTYP_SELFTEST

The component failed self test.


##### - ErrorType.ERRTYP_TIMEOUT

A bus timeout error.


##### - ErrorType.ERRTYP_TLB

A translation lookaside buffer error.


##### - ErrorType.ERRTYP_UNIMPL

An access to a memory address that is not mapped to any component.


## -remarks



The WHEA_ERROR_STATUS union provides the capability to abstract information from implementation-specific error registers into generic error codes so that the operating system can process the errors without an intimate knowledge of the underlying platform. This union is derived from the Error Status section of the <a href="http://go.microsoft.com/fwlink/p/?linkid=26730">Intel Itanium Processor Family System Abstraction Layer Specification</a>.

A WHEA_ERROR_STATUS union is contained within the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560565">WHEA_MEMORY_ERROR_SECTION</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff560583">WHEA_PCIXBUS_ERROR_SECTION</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff560589">WHEA_PCIXDEVICE_ERROR_SECTION</a> structures.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560565">WHEA_MEMORY_ERROR_SECTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560583">WHEA_PCIXBUS_ERROR_SECTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560589">WHEA_PCIXDEVICE_ERROR_SECTION</a>
 

 

