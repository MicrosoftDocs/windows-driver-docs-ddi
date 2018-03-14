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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	WHEA_ERROR_STATUS
product: Windows
targetos: Windows
req.typenames: WHEA_ERROR_STATUS, *PWHEA_ERROR_STATUS
---

# _WHEA_ERROR_STATUS structure


## -description


The WHEA_ERROR_STATUS union describes generic error codes that are abstracted from the data contained in implementation-specific error registers.


## -syntax


````
typedef union _WHEA_ERROR_STATUS {
  ULONGLONG ErrorStatus;
  struct {
    ULONGLONG Reserved1  :8;
    ULONGLONG ErrorType  :8;
    ULONGLONG Address  :1;
    ULONGLONG Control  :1;
    ULONGLONG Data  :1;
    ULONGLONG Responder  :1;
    ULONGLONG Requester  :1;
    ULONGLONG FirstError  :1;
    ULONGLONG Overflow  :1;
    ULONGLONG Reserved2  :41;
  };
} WHEA_ERROR_STATUS, *PWHEA_ERROR_STATUS;
````


## -struct-fields




### -field ErrorStatus

A ULONGLONG representation of the contents of the WHEA_ERROR_STATUS union.


### -field DUMMYSTRUCTNAME

 




#### - Address

A single bit that indicates if the error was detected on the address signals or during the address portion of the transaction.


#### - Control

A single bit that indicates if the error was detected on the control signals or during the control portion of the transaction.


#### - Data

A single bit that indicates if the error was detected on the data signals or during the data portion of the transaction.


#### - ErrorType

The type of hardware error that occurred. Possible values are:





#### ERRTYP_INTERNAL

An error internal to the component.



#### ERRTYP_BUS

A bus error.



#### ERRTYP_MEM

A memory error.



#### ERRTYP_TLB

A translation lookaside buffer error.



#### ERRTYP_CACHE

A cache error.



#### ERRTYP_FUNCTION

An error in one or more functional units.



#### ERRTYP_SELFTEST

The component failed self test.



#### ERRTYP_FLOW

An overflow or underflow of a queue that is internal to the component.



#### ERRTYP_MAP

The virtual address was not found on IO-TLB or IO-PDIR.



#### ERRTYP_IMPROPER

An improper access error.



#### ERRTYP_UNIMPL

An access to a memory address that is not mapped to any component.



#### ERRTYP_LOSSOFLOCKSTEP

A loss of lockstep.



#### ERRTYP_RESPONSE

A response was received that was not associated with a request.



#### ERRTYP_PARITY

A bus parity error.



#### ERRTYP_PROTOCOL

A bus protocol error.



#### ERRTYP_PATHERROR

A bus path error.



#### ERRTYP_TIMEOUT

A bus timeout error.



#### ERRTYP_POISONED

A read operation was issued to data that has been corrupted.


#### - FirstError

A single bit that indicates that the error is the first error to occur if multiple errors are logged for a section type. Setting of this bit is optional.


#### - Overflow

A single bit that indicates that additional errors occurred but were not logged due to an overflow of the logging resources.


#### - Requester

A single bit that indicates that the error was detected by the requester of the transaction.


#### - Reserved1

Reserved for system use.


#### - Reserved2

Reserved for system use.


#### - Responder

A single bit that indicates that the error was detected by the responder of the transaction.


## -remarks



The WHEA_ERROR_STATUS union provides the capability to abstract information from implementation-specific error registers into generic error codes so that the operating system can process the errors without an intimate knowledge of the underlying platform. This union is derived from the Error Status section of the <a href="http://go.microsoft.com/fwlink/p/?linkid=26730">Intel Itanium Processor Family System Abstraction Layer Specification</a>.

A WHEA_ERROR_STATUS union is contained within the <a href="..\ntddk\ns-ntddk-_whea_memory_error_section.md">WHEA_MEMORY_ERROR_SECTION</a>, <a href="..\ntddk\ns-ntddk-_whea_pcixbus_error_section.md">WHEA_PCIXBUS_ERROR_SECTION</a>, and <a href="..\ntddk\ns-ntddk-_whea_pcixdevice_error_section.md">WHEA_PCIXDEVICE_ERROR_SECTION</a> structures.




## -see-also

<a href="..\ntddk\ns-ntddk-_whea_pcixbus_error_section.md">WHEA_PCIXBUS_ERROR_SECTION</a>



<a href="..\ntddk\ns-ntddk-_whea_memory_error_section.md">WHEA_MEMORY_ERROR_SECTION</a>



<a href="..\ntddk\ns-ntddk-_whea_pcixdevice_error_section.md">WHEA_PCIXDEVICE_ERROR_SECTION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_ERROR_STATUS union%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

