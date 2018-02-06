---
UID: NS:ntddk._WHEA_XPF_BUS_CHECK
title: "_WHEA_XPF_BUS_CHECK"
author: windows-driver-content
description: The WHEA_XPF_BUS_CHECK union describes bus error information for an x86 or x64 processor.
old-location: whea\whea_xpf_bus_check.htm
old-project: whea
ms.assetid: 7886a796-2755-4367-bbbd-2017e7900bf4
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: "*PWHEA_XPF_BUS_CHECK, WHEA_XPF_BUS_CHECK, ntddk/WHEA_XPF_BUS_CHECK, _WHEA_XPF_BUS_CHECK, PWHEA_XPF_BUS_CHECK, PWHEA_XPF_BUS_CHECK union pointer [WHEA Drivers and Applications], whea.whea_xpf_bus_check, WHEA_XPF_BUS_CHECK union [WHEA Drivers and Applications], ntddk/PWHEA_XPF_BUS_CHECK, whearef_fff50a8d-8ab0-4f25-adb3-b33e1ea80aed.xml"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	WHEA_XPF_BUS_CHECK
product: Windows
targetos: Windows
req.typenames: WHEA_XPF_BUS_CHECK, *PWHEA_XPF_BUS_CHECK
---

# _WHEA_XPF_BUS_CHECK structure


## -description


The WHEA_XPF_BUS_CHECK union describes bus error information for an x86 or x64 processor.


## -syntax


````
typedef union _WHEA_XPF_BUS_CHECK {
  struct {
    ULONGLONG TransactionTypeValid  :1;
    ULONGLONG OperationValid  :1;
    ULONGLONG LevelValid  :1;
    ULONGLONG ProcessorContextCorruptValid  :1;
    ULONGLONG UncorrectedValid  :1;
    ULONGLONG PreciseIPValid  :1;
    ULONGLONG RestartableIPValid  :1;
    ULONGLONG OverflowValid  :1;
    ULONGLONG ParticipationValid  :1;
    ULONGLONG TimeoutValid  :1;
    ULONGLONG AddressSpaceValid  :1;
    ULONGLONG ReservedValid  :5;
    ULONGLONG TransactionType  :2;
    ULONGLONG Operation  :4;
    ULONGLONG Level  :3;
    ULONGLONG ProcessorContextCorrupt  :1;
    ULONGLONG Uncorrected  :1;
    ULONGLONG PreciseIP  :1;
    ULONGLONG RestartableIP  :1;
    ULONGLONG Overflow  :1;
    ULONGLONG Participation  :2;
    ULONGLONG Timeout  :1;
    ULONGLONG AddressSpace  :2;
    ULONGLONG Reserved  :29;
  };
  ULONGLONG XpfBusCheck;
} WHEA_XPF_BUS_CHECK, *PWHEA_XPF_BUS_CHECK;
````


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field DUMMYSTRUCTNAME.TransactionTypeValid

A single bit that indicates that the <b>TransactionType</b> member contains valid data.


### -field DUMMYSTRUCTNAME.OperationValid

A single bit that indicates that the <b>Operation</b> member contains valid data.


### -field DUMMYSTRUCTNAME.LevelValid

A single bit that indicates that the <b>Level</b> member contains valid data.


### -field DUMMYSTRUCTNAME.ProcessorContextCorruptValid

A single bit that indicates that the <b>ProcessorContextCorrupt</b> member contains valid data.


### -field DUMMYSTRUCTNAME.UncorrectedValid

A single bit that indicates that the <b>Uncorrected </b>member contains valid data.


### -field DUMMYSTRUCTNAME.PreciseIPValid

A single bit that indicates that the <b>PreciseIP</b> member contains valid data.


### -field DUMMYSTRUCTNAME.RestartableIPValid

A single bit that indicates that the <b>RestartableIP</b> member contains valid data.


### -field DUMMYSTRUCTNAME.OverflowValid

A single bit that indicates that the <b>Overflow</b> member contains valid data.


### -field DUMMYSTRUCTNAME.ParticipationValid

A single bit that indicates that the <b>Participation</b> member contains valid data.


### -field DUMMYSTRUCTNAME.TimeoutValid

A single bit that indicates that the <b>Timeout</b> member contains valid data.


### -field DUMMYSTRUCTNAME.AddressSpaceValid

A single bit that indicates that the <b>AddressSpace</b> member contains valid data.


### -field DUMMYSTRUCTNAME.ReservedValid

Reserved for system use.


### -field DUMMYSTRUCTNAME.TransactionType

The type of transaction that was in progress when the error occurred. Possible values are:



This member contains valid data only if the <b>TransactionTypeValid</b> bit is set.


### -field DUMMYSTRUCTNAME.Operation

The type of bus operation that caused the error. Possible values are:



This member contains valid data only if the <b>OperationValid</b> bit is set.


### -field DUMMYSTRUCTNAME.Level

The level of the bus hierarchy where the error occurred.

This member contains valid data only if the <b>LevelValid</b> bit is set.


### -field DUMMYSTRUCTNAME.ProcessorContextCorrupt

A single bit that indicates that the processor context might have been corrupted.

This member contains valid data only if the <b>ProcessorContextCorruptValid</b> bit is set.


### -field DUMMYSTRUCTNAME.Uncorrected

A single bit that indicates that the error has not been corrected.

This member contains valid data only if the <b>UncorrectedValid</b> bit is set.


### -field DUMMYSTRUCTNAME.PreciseIP

A single bit that indicates that the instruction pointer that is specified in the <b>InstructionPointer</b> member of the <a href="..\ntddk\ns-ntddk-_whea_xpf_procinfo.md">WHEA_XPF_PROCINFO</a> structure that contains this WHEA_XPF_BUS_CHECK union is directly associated with the error.

This member contains valid data only if the <b>PreciseIPValid</b> bit is set.


### -field DUMMYSTRUCTNAME.RestartableIP

A single bit that indicates that program execution can be restarted reliably at the instruction pointer that is specified in the <b>InstructionPointer</b> member of the <a href="..\ntddk\ns-ntddk-_whea_xpf_procinfo.md">WHEA_XPF_PROCINFO</a> union that contains this WHEA_XPF_BUS_CHECK structure.

This member contains valid data only if the <b>RestartableIPValid</b> bit is set.


### -field DUMMYSTRUCTNAME.Overflow

A single bit that indicates that an error overflow occurred.

This member contains valid data only if the <b>OverflowValid</b> bit is set.


### -field DUMMYSTRUCTNAME.Participation

The type of participation by the local processor. Possible values are:



This member contains valid data only if the <b>ParticipationValid</b> bit is set.


### -field DUMMYSTRUCTNAME.Timeout

A single bit that indicates that a timeout occurred.

This member contains valid data only if the <b>TimeoutValid</b> bit is set.


### -field DUMMYSTRUCTNAME.AddressSpace

The type of address space that was associated with the transaction that caused the error. Possible values are:



This member contains valid data only if the <b>AddressSpaceValid</b> bit is set.


### -field DUMMYSTRUCTNAME.Reserved

Reserved for system use.


### -field XpfBusCheck

A ULONGLONG representation of the contents of the WHEA_XPF_BUS_CHECK union.


##### - TransactionType.XPF_BUS_CHECK_TRANSACTIONTYPE_INSTRUCTION

A processor instruction transaction.


##### - TransactionType.XPF_BUS_CHECK_TRANSACTIONTYPE_DATAACCESS

A data access transaction.


##### - TransactionType.XPF_BUS_CHECK_TRANSACTIONTYPE_GENERIC

A generic transaction.


##### - Operation.XPF_BUS_CHECK_OPERATION_GENERIC

The type of operation cannot be determined.


##### - Operation.XPF_BUS_CHECK_OPERATION_GENREAD

A generic read operation.


##### - Operation.XPF_BUS_CHECK_OPERATION_GENWRITE

A generic write operation.


##### - Operation.XPF_BUS_CHECK_OPERATION_DATAREAD

A data read operation.


##### - Operation.XPF_BUS_CHECK_OPERATION_DATAWRITE

A data write operation.


##### - Operation.XPF_BUS_CHECK_OPERATION_INSTRUCTIONFETCH

An instruction fetch operation.


##### - Operation.XPF_BUS_CHECK_OPERATION_PREFETCH

An instruction prefetch operation.


##### - Participation.XPF_BUS_CHECK_PARTICIPATION_PROCORIGINATED

The local processor originated the request.


##### - Participation.XPF_BUS_CHECK_PARTICIPATION_PROCRESPONDED

The local processor responded to the request.


##### - Participation.XPF_BUS_CHECK_PARTICIPATION_PROCOBSERVED

The local processor observed the request.


##### - Participation.XPF_BUS_CHECK_PARTICIPATION_GENERIC

A generic value for this member if none of the other values are applicable.


##### - AddressSpace.XPF_BUS_CHECK_ADDRESS_MEMORY

Memory address space.


##### - AddressSpace.XPF_BUS_CHECK_ADDRESS_RESERVED

Reserved.


##### - AddressSpace.XPF_BUS_CHECK_ADDRESS_IO

I/O address space.


##### - AddressSpace.XPF_BUS_CHECK_ADDRESS_OTHER

An unclassified type of address space.


## -remarks


If the <b>CheckInfoId</b> member of a <a href="..\ntddk\ns-ntddk-_whea_xpf_procinfo.md">WHEA_XPF_PROCINFO</a> structure contains WHEA_BUSCHECK_GUID, the <b>CheckInfo</b> member of the WHEA_XPF_PROCINFO structure contains a WHEA_XPF_BUS_CHECK union.



## -see-also

<a href="..\ntddk\ns-ntddk-_whea_xpf_procinfo.md">WHEA_XPF_PROCINFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_XPF_BUS_CHECK union%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

