---
UID: NC:ntddk.pHalQuerySystemInformation
title: pHalQuerySystemInformation
description: 
ms.assetid: 1470096d-c598-4724-9107-10678ae46a71
ms.date: 10/19/2018
ms.topic: callback
req.header: ntddk.h
req.include-header:
req.target-type: Desktop
req.target-min-winverclnt:
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
-	ntddk.h
api_name: 
-	pHalQuerySystemInformation
product:
-	Windows
targetos: Windows
---

# pHalQuerySystemInformation callback function

## -description

Read MCA banks' status registers. 

## -prototype

```cpp
//Declaration

pHalQuerySystemInformation Phalquerysysteminformation; 

// Definition

NTSTATUS Phalquerysysteminformation 
(
	HAL_QUERY_INFORMATION_CLASS InformationClass
	ULONG BufferSize
	PVOID Buffer
	PULONG ReturnedLength
)
{...}

pHalQuerySystemInformation 


```

## -parameters

### -param InformationClass
[in] The HalMcaLogInformation to read the current MCA error log. If any of the uncorrected Machine Check errors is found, it is returned in the buffer. For Itanium systems, specify HalCmcLogInformation to read the current corrected CPU error log and HalCpeLogInformation to read the current corrected platform error log.
### -param BufferSize
[in] The size, in bytes, of the buffer that the caller supplies.
### -param Buffer
[out] A pointer to a caller-supplied buffer of type MCA_EXCEPTION that will contain the information returned by this routine. For Intel Itanium processors, the returned information must be compliant, at a minimum, with the V3.0 SAL specification, Error Record Structures, January 2001, Appendix B"". For Intel Pentium Pro processors, the information is as described in the following code example.
```cpp
typedef union _MCI_STATS {
  struct {
    USHORT  McaCod;
    USHORT  MsCod;
    ULONG  OtherInfo   : 25;
    ULONG  Damage    : 1;
    ULONG  AddressValid  : 1;
    ULONG  MiscValid  : 1;
    ULONG  Enabled    : 1;
    ULONG  UnCorrected  : 1;
    ULONG  OverFlow  : 1;
    ULONG  Valid    : 1;
  } MciStats;

  ULONGLONG  QuadPart;
} MCI_STATS, *PMCI_STATS;


typedef union _MCI_ADDR{
  struct {
    ULONG Address;
    ULONG Reserved;
  } MciAddr;

  ULONGLONG  QuadPart;
} MCI_ADDR, *PMCI_ADDR;


typedef struct _MCA_EXCEPTION {

  ULONG  VersionNumber;  // Version number of this record type
  MCA_EXCEPTION_TYPE  ExceptionType;  // MCA or MCE
  LARGE_INTEGER  TimeStamp;  // exception recording timestamp
  ULONG  ProcessorNumber;// processor number

  union {
    struct {
      UCHAR  BankNumber;  // bank number
      MCI_STATS  Status;  
      MCI_ADDR  Address;
      ULONGLONG  Misc;
    } Mca;

    struct {
      ULONGLONG  McAddress;  // physical address for the cycle causing the error
      ULONGLONG  McType;   // cycle specification causing the error
    } Mce;
  } u;

} MCA_EXCEPTION, *PMCA_EXCEPTION;
```

### -param ReturnedLength
[out] The number of bytes that are returned in Buffer.


## -returns

Returns STATUS_SUCCESS if an error log exists.

## -remarks

The **HalQuerySystemInformation** function returns the first error. It is the MCA driver's responsibility to call this routine again to see if there are any more errors available.
>Windows Vista and later versions of Windows do not support the type of Machine Check Architecture (MCA) and Machine Check Exception (MCE) reporting that is described in this topic. MCA and MCE reporting are supported through [Windows Hardware Error Architecture (WHEA)](https://msdn.microsoft.com/library/Ff559509) instead.


## -see-also
