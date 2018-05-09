---
UID: NS:ntddk._WHEA_PROCESSOR_FAMILY_INFO
title: "_WHEA_PROCESSOR_FAMILY_INFO"
author: windows-driver-content
description: The WHEA_PROCESSOR_FAMILY_INFO union describes the processor family information for an x86 or x64 processor.
old-location: whea\whea_processor_family_info.htm
old-project: whea
ms.assetid: cc20c2d6-c76b-4f72-9762-23b9aa5fe946
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWHEA_PROCESSOR_FAMILY_INFO, PWHEA_PROCESSOR_FAMILY_INFO, PWHEA_PROCESSOR_FAMILY_INFO union pointer [WHEA Drivers and Applications], WHEA_PROCESSOR_FAMILY_INFO, WHEA_PROCESSOR_FAMILY_INFO union [WHEA Drivers and Applications], _WHEA_PROCESSOR_FAMILY_INFO, ntddk/PWHEA_PROCESSOR_FAMILY_INFO, ntddk/WHEA_PROCESSOR_FAMILY_INFO, whea.whea_processor_family_info, whearef_f15c7bb5-aee5-4a59-9869-285828d92b5e.xml"
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
-	WHEA_PROCESSOR_FAMILY_INFO
product:
- Windows
targetos: Windows
req.typenames: WHEA_PROCESSOR_FAMILY_INFO, *PWHEA_PROCESSOR_FAMILY_INFO
---

# _WHEA_PROCESSOR_FAMILY_INFO structure


## -description


The WHEA_PROCESSOR_FAMILY_INFO union describes the processor family information for an x86 or x64 processor.


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field DUMMYSTRUCTNAME.Stepping

The stepping of the processor.


### -field DUMMYSTRUCTNAME.Model

The processor model identifier.


### -field DUMMYSTRUCTNAME.Family

The processor family identifier.


### -field DUMMYSTRUCTNAME.ProcessorType

The processor type identifier.


### -field DUMMYSTRUCTNAME.Reserved1

Reserved for system use.


### -field DUMMYSTRUCTNAME.ExtendedModel

The extended processor model identifier.


### -field DUMMYSTRUCTNAME.ExtendedFamily

The extended processor family identifier.


### -field DUMMYSTRUCTNAME.Reserved2

Reserved for system use.


### -field DUMMYSTRUCTNAME.Reserved3

Reserved for system use.


### -field AsULONGLONG

A ULONGLONG representation of the contents of the WHEA_PROCESSOR_FAMILY_INFO union.


## -remarks



For x86 and x64 processors, the <b>CPUVersion</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560607">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a> structure contains a WHEA_PROCESSOR_FAMILY_INFO union.

The contents of this union are obtained by executing the CPUID instruction with the EAX register set to 1 on input. For more information about the CPUID instruction, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=78804">Intel 64 and IA-32 Architectures Software Developer's Manual</a>. For additional information about the data that is contained in the members of this union, see <a href="http://go.microsoft.com/fwlink/p/?linkid=80097">AP-485 Intel Processor Identification and the CPUID Instruction</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560607">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a>
 

 

