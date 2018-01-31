---
UID: NS:ndis._NDIS_SYSTEM_PROCESSOR_INFO
title: "_NDIS_SYSTEM_PROCESSOR_INFO"
author: windows-driver-content
description: The NDIS_SYSTEM_PROCESSOR_INFO structure specifies information about the CPU topology of the local computer and the receive side scaling (RSS) processor set.
old-location: netvista\ndis_system_processor_info.htm
old-project: netvista
ms.assetid: f59b9394-7742-423d-9a6e-3a429ccb0740
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndis_system_processor_info, PNDIS_SYSTEM_PROCESSOR_INFO, PNDIS_SYSTEM_PROCESSOR_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SYSTEM_PROCESSOR_INFO, NDIS_SYSTEM_PROCESSOR_INFO, ndis_sysinfo_ref_79dba975-da34-4cc1-b26b-5c18867fa408.xml, *PNDIS_SYSTEM_PROCESSOR_INFO, NDIS_SYSTEM_PROCESSOR_INFO structure [Network Drivers Starting with Windows Vista], ndis/NDIS_SYSTEM_PROCESSOR_INFO, ndis/PNDIS_SYSTEM_PROCESSOR_INFO
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
req.irql: See Remarks section
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	NDIS_SYSTEM_PROCESSOR_INFO
product: Windows
targetos: Windows
req.typenames: NDIS_SYSTEM_PROCESSOR_INFO, *PNDIS_SYSTEM_PROCESSOR_INFO
---

# _NDIS_SYSTEM_PROCESSOR_INFO structure


## -description


The <b>NDIS_SYSTEM_PROCESSOR_INFO</b> structure specifies information about the CPU topology of the local
  computer and the receive side scaling (RSS) processor set.


## -syntax


````
typedef struct _NDIS_SYSTEM_PROCESSOR_INFO {
  NDIS_OBJECT_HEADER    Header;
  ULONG                 Flags;
  NDIS_PROCESSOR_VENDOR ProcessorVendor;
  ULONG                 NumPhysicalPackages;
  ULONG                 NumCores;
  ULONG                 NumCoresPerPhysicalPackage;
  ULONG                 MaxHyperThreadingCpusPerCore;
  ULONG                 RssBaseCpu;
  ULONG                 RssCpuCount;
  PUCHAR                RssProcessors;
  NDIS_PROCESSOR_INFO   CpuInfo[MAXIMUM_PROC_PER_GROUP];
} NDIS_SYSTEM_PROCESSOR_INFO, *PNDIS_SYSTEM_PROCESSOR_INFO;
````


## -struct-fields




#### - Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_SYSTEM_PROCESSOR_INFO structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_SYSTEM_PROCESSOR_INFO_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_SYSTEM_PROCESSOR_INFO_REVISION_1.


#### - Flags

Reserved. Set this member to zero.


#### - ProcessorVendor

The processor vendor specified as one of the values from the 
     <mshelp:link keywords="netvista.ndis_processor_vendor" tabindex="0"><b>
     NDIS_PROCESSOR_VENDOR</b></mshelp:link> enumeration.


#### - NumPhysicalPackages

The total number of processor physical packages that are in the local computer.


#### - NumCores

The total number of core processors that are in the local computer. For example, set this member
     to four if there are two dual core physical packages.


#### - NumCoresPerPhysicalPackage

The number of core processors that are in each physical package. For example, set this member to
     two for a dual core physical package.


#### - MaxHyperThreadingCpusPerCore

The maximum number of logical processors that are in each hyper-threaded core processor. For
     example, set this member to two if each hyper-threaded core processor supports two logical
     processors.


#### - RssBaseCpu

The starting CPU number that is used for RSS.


#### - RssCpuCount

The number of processors that are used for RSS.


#### - RssProcessors

A pointer to an optional caller-provided buffer that will contain the CPU numbers of the
     processors that can be used for RSS. Set this member to <b>NULL</b> if the CPU numbers are not required. To
     obtain CPU numbers, this member must contain a valid pointer and the size of this buffer must be at
     least 
     <b>MAXIMUM_PROCESSORS * sizeof (UCHAR)</b>. After the 
     <mshelp:link keywords="netvista.ndisgetprocessorinformation" tabindex="0"><b>
     NdisGetProcessorInformation</b></mshelp:link> function returns successfully, the buffer contains CPU numbers
     followed by undefined data.


#### - CpuInfo

An array of 
     <a href="..\ndis\ns-ndis-_ndis_processor_info.md">NDIS_PROCESSOR_INFO</a> structures. After
     the 
     <b>NdisGetProcessorInformation</b> function returns successfully, this array provides information for
     each processor in the local computer. The number of values in the array is equal to the number of
     processors in the local computer, as the 
     <mshelp:link keywords="netvista.ndissystemactiveprocessorcount" tabindex="0"><b>
     NdisSystemActiveProcessorCount</b></mshelp:link> function reports.


## -remarks


NDIS network drivers use the NDIS_SYSTEM_PROCESSOR_INFO structure in calls to the 
    <mshelp:link keywords="netvista.ndisgetprocessorinformation" tabindex="0"><b>
    NdisGetProcessorInformation</b></mshelp:link> function. After 
    <b>NdisGetProcessorInformation</b> returns, this structure contains information about the CPU topology of
    the system and the set of processors that will be used for receive side scaling (RSS).



## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<a href="..\ntddndis\ne-ntddndis-_ndis_processor_vendor.md">NDIS_PROCESSOR_VENDOR</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_system_processor_info_ex.md">NDIS_SYSTEM_PROCESSOR_INFO_EX</a>

<mshelp:link keywords="netvista.ndissystemactiveprocessorcount" tabindex="0"><b>
   NdisSystemActiveProcessorCount</b></mshelp:link>

<a href="..\ndis\nf-ndis-ndisgetprocessorinformation.md">NdisGetProcessorInformation</a>

<a href="..\ndis\ns-ndis-_ndis_processor_info.md">NDIS_PROCESSOR_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SYSTEM_PROCESSOR_INFO structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

