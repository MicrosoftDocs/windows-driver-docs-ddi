---
UID: NS:ntddk._WHEA_XPF_TLB_CHECK
title: "_WHEA_XPF_TLB_CHECK"
author: windows-driver-content
description: The WHEA_XPF_TLB_CHECK union describes translation lookaside buffer (TLB) error information for an x86 or x64 processor.
old-location: whea\whea_xpf_tlb_check.htm
tech.root: whea
ms.assetid: 3943c854-3bb9-4fc9-9af9-735c3f4ee94e
ms.date: 02/20/2018
ms.keywords: "*PWHEA_XPF_TLB_CHECK, PWHEA_XPF_TLB_CHECK, PWHEA_XPF_TLB_CHECK union pointer [WHEA Drivers and Applications], WHEA_XPF_TLB_CHECK, WHEA_XPF_TLB_CHECK union [WHEA Drivers and Applications], _WHEA_XPF_TLB_CHECK, ntddk/PWHEA_XPF_TLB_CHECK, ntddk/WHEA_XPF_TLB_CHECK, whea.whea_xpf_tlb_check, whearef_20ed4273-105d-467b-a71f-46e50078543e.xml"
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
-	WHEA_XPF_TLB_CHECK
product:
- Windows
targetos: Windows
req.typenames: WHEA_XPF_TLB_CHECK, *PWHEA_XPF_TLB_CHECK
---

# _WHEA_XPF_TLB_CHECK structure


## -description


The WHEA_XPF_TLB_CHECK union describes translation lookaside buffer (TLB) error information for an x86 or x64 processor.


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

A single bit that indicates that the <b>Uncorrected</b> member contains valid data.


### -field DUMMYSTRUCTNAME.PreciseIPValid

A single bit that indicates that the <b>PreciseIP</b> member contains valid data.


### -field DUMMYSTRUCTNAME.RestartableIPValid

A single bit that indicates that the <b>RestartableIP</b> member contains valid data.


### -field DUMMYSTRUCTNAME.OverflowValid

A single bit that indicates that the <b>Overflow</b> member contains valid data.


### -field DUMMYSTRUCTNAME.ReservedValid

Reserved for system use.


### -field DUMMYSTRUCTNAME.TransactionType

The type of transaction that was in progress when the error occurred. Possible values are:



This member contains valid data only if the <b>TransactionTypeValid</b> bit is set.


### -field DUMMYSTRUCTNAME.Operation

The type of translation lookaside buffer (TLB) access operation that caused the error. Possible values are:



This member contains valid data only if the <b>OperationValid</b> bit is set.


### -field DUMMYSTRUCTNAME.Level

The level of the TLB where the error occurred.

This member contains valid data only if the <b>LevelValid</b> bit is set.


### -field DUMMYSTRUCTNAME.ProcessorContextCorrupt

A single bit that indicates that the processor context might have been corrupted.

This member contains valid data only if the <b>ProcessorContextCorruptValid</b> bit is set.


### -field DUMMYSTRUCTNAME.Uncorrected

A single bit that indicates that the error has not been corrected.

This member contains valid data only if the <b>UncorrectedValid</b> bit is set.


### -field DUMMYSTRUCTNAME.PreciseIP

A single bit that indicates that the instruction pointer that is specified in the <b>InstructionPointer</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560661">WHEA_XPF_PROCINFO</a> structure that contains this WHEA_XPF_TLB_CHECK union is directly associated with the error.

This member contains valid data only if the <b>PreciseIPValid</b> bit is set.


### -field DUMMYSTRUCTNAME.RestartableIP

A single bit that indicates that program execution can be restarted reliably at the instruction pointer that is specified in the <b>InstructionPointer</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560661">WHEA_XPF_PROCINFO</a> union that contains this WHEA_XPF_TLB_CHECK structure.

This member contains valid data only if the <b>RestartableIPValid</b> bit is set.


### -field DUMMYSTRUCTNAME.Overflow

A single bit that indicates that an error overflow occurred.

This member contains valid data only if the <b>OverflowValid</b> bit is set.


### -field DUMMYSTRUCTNAME.Reserved

Reserved for system use.


### -field XpfTLBCheck

A ULONGLONG representation of the contents of the WHEA_XPF_TLB_CHECK union.


##### - Operation.XPF_TLB_CHECK_OPERATION_DATAREAD

A data read operation.


##### - Operation.XPF_TLB_CHECK_OPERATION_DATAWRITE

A data write operation.


##### - Operation.XPF_TLB_CHECK_OPERATION_GENERIC

The type of operation cannot be determined.


##### - Operation.XPF_TLB_CHECK_OPERATION_GENREAD

A generic read operation.


##### - Operation.XPF_TLB_CHECK_OPERATION_GENWRITE

A generic write operation.


##### - Operation.XPF_TLB_CHECK_OPERATION_INSTRUCTIONFETCH

An instruction fetch operation.


##### - Operation.XPF_TLB_CHECK_OPERATION_PREFETCH

An instruction prefetch operation.


##### - TransactionType.XPF_TLB_CHECK_TRANSACTIONTYPE_DATAACCESS

A data access transaction.


##### - TransactionType.XPF_TLB_CHECK_TRANSACTIONTYPE_GENERIC

A generic transaction.


##### - TransactionType.XPF_TLB_CHECK_TRANSACTIONTYPE_INSTRUCTION

A processor instruction transaction.


## -remarks



If the <b>CheckInfoId</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560661">WHEA_XPF_PROCINFO</a> structure contains WHEA_TLBCHECK_GUID, the <b>CheckInfo</b> member of the WHEA_XPF_PROCINFO structure contains a WHEA_XPF_TLB_CHECK union.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560661">WHEA_XPF_PROCINFO</a>
 

 

