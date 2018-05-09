---
UID: NS:ndis._NDIS_SYSTEM_PROCESSOR_INFO
title: "_NDIS_SYSTEM_PROCESSOR_INFO"
author: windows-driver-content
description: The NDIS_SYSTEM_PROCESSOR_INFO structure specifies information about the CPU topology of the local computer and the receive side scaling (RSS) processor set.
old-location: netvista\ndis_system_processor_info.htm
old-project: netvista
ms.assetid: f59b9394-7742-423d-9a6e-3a429ccb0740
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PNDIS_SYSTEM_PROCESSOR_INFO, NDIS_SYSTEM_PROCESSOR_INFO, NDIS_SYSTEM_PROCESSOR_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_SYSTEM_PROCESSOR_INFO, PNDIS_SYSTEM_PROCESSOR_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SYSTEM_PROCESSOR_INFO, ndis/NDIS_SYSTEM_PROCESSOR_INFO, ndis/PNDIS_SYSTEM_PROCESSOR_INFO, ndis_sysinfo_ref_79dba975-da34-4cc1-b26b-5c18867fa408.xml, netvista.ndis_system_processor_info"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and 6.1. For NDIS 6.20 and later, use NDIS_SYSTEM_PROCESSOR_INFO_EX.
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
-	ndis.h
api_name:
-	NDIS_SYSTEM_PROCESSOR_INFO
product:
- Windows
targetos: Windows
req.typenames: NDIS_SYSTEM_PROCESSOR_INFO, *PNDIS_SYSTEM_PROCESSOR_INFO
---

# _NDIS_SYSTEM_PROCESSOR_INFO structure


## -description


The <b>NDIS_SYSTEM_PROCESSOR_INFO</b> structure specifies information about the CPU topology of the local
  computer and the receive side scaling (RSS) processor set.


## -struct-fields




### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_SYSTEM_PROCESSOR_INFO structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_SYSTEM_PROCESSOR_INFO_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_SYSTEM_PROCESSOR_INFO_REVISION_1.


### -field Flags

Reserved. Set this member to zero.


### -field ProcessorVendor

The processor vendor specified as one of the values from the 
     <a href="https://msdn.microsoft.com/c2d1b967-32fb-437a-a0bd-e0028acee022">
     NDIS_PROCESSOR_VENDOR</a> enumeration.


### -field NumPhysicalPackages

The total number of processor physical packages that are in the local computer.


### -field NumCores

The total number of core processors that are in the local computer. For example, set this member
     to four if there are two dual core physical packages.


### -field NumCoresPerPhysicalPackage

The number of core processors that are in each physical package. For example, set this member to
     two for a dual core physical package.


### -field MaxHyperThreadingCpusPerCore

The maximum number of logical processors that are in each hyper-threaded core processor. For
     example, set this member to two if each hyper-threaded core processor supports two logical
     processors.


### -field RssBaseCpu

The starting CPU number that is used for RSS.


### -field RssCpuCount

The number of processors that are used for RSS.


### -field RssProcessors

A pointer to an optional caller-provided buffer that will contain the CPU numbers of the
     processors that can be used for RSS. Set this member to <b>NULL</b> if the CPU numbers are not required. To
     obtain CPU numbers, this member must contain a valid pointer and the size of this buffer must be at
     least 
     <b>MAXIMUM_PROCESSORS * sizeof (UCHAR)</b>. After the 
     <a href="https://msdn.microsoft.com/2cee5cf4-7dee-49d2-905c-2b9634137ce4">
     NdisGetProcessorInformation</a> function returns successfully, the buffer contains CPU numbers
     followed by undefined data.


### -field CpuInfo

An array of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566808">NDIS_PROCESSOR_INFO</a> structures. After
     the 
     <b>NdisGetProcessorInformation</b> function returns successfully, this array provides information for
     each processor in the local computer. The number of values in the array is equal to the number of
     processors in the local computer, as the 
     <a href="https://msdn.microsoft.com/7ddb54eb-9f20-4cb9-8488-5f2806d23430">
     NdisSystemActiveProcessorCount</a> function reports.


## -remarks



NDIS network drivers use the NDIS_SYSTEM_PROCESSOR_INFO structure in calls to the 
    <a href="https://msdn.microsoft.com/2cee5cf4-7dee-49d2-905c-2b9634137ce4">
    NdisGetProcessorInformation</a> function. After 
    <b>NdisGetProcessorInformation</b> returns, this structure contains information about the CPU topology of
    the system and the set of processors that will be used for receive side scaling (RSS).




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566808">NDIS_PROCESSOR_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566813">NDIS_PROCESSOR_VENDOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567872">NDIS_SYSTEM_PROCESSOR_INFO_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562661">NdisGetProcessorInformation</a>



<a href="https://msdn.microsoft.com/7ddb54eb-9f20-4cb9-8488-5f2806d23430">
   NdisSystemActiveProcessorCount</a>
 

 

