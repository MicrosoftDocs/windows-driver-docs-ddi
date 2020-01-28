---
UID: NS:ntddndis._NDIS_SYSTEM_PROCESSOR_INFO_EX
title: _NDIS_SYSTEM_PROCESSOR_INFO_EX (ntddndis.h)
description: The NDIS_SYSTEM_PROCESSOR_INFO_EX structure specifies information about the CPU topology of the local computer.
old-location: netvista\ndis_system_processor_info_ex.htm
tech.root: netvista
ms.assetid: ba3c6641-98bc-4c44-9889-7583c4cf61f0
ms.date: 05/02/2018
ms.keywords: "*PNDIS_SYSTEM_PROCESSOR_INFO_EX, NDIS_SYSTEM_PROCESSOR_INFO_EX, NDIS_SYSTEM_PROCESSOR_INFO_EX structure [Network Drivers Starting with Windows Vista], PNDIS_SYSTEM_PROCESSOR_INFO_EX, PNDIS_SYSTEM_PROCESSOR_INFO_EX structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SYSTEM_PROCESSOR_INFO_EX, ndis_processor_group_ref_754737d7-8279-4786-b89d-4326da949464.xml, netvista.ndis_system_processor_info_ex, ntddndis/NDIS_SYSTEM_PROCESSOR_INFO_EX, ntddndis/PNDIS_SYSTEM_PROCESSOR_INFO_EX"
f1_keywords:
 - "ntddndis/NDIS_SYSTEM_PROCESSOR_INFO_EX"
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddndis.h
api_name:
- NDIS_SYSTEM_PROCESSOR_INFO_EX
product:
- Windows
targetos: Windows
req.typenames: NDIS_SYSTEM_PROCESSOR_INFO_EX, *PNDIS_SYSTEM_PROCESSOR_INFO_EX
---

# _NDIS_SYSTEM_PROCESSOR_INFO_EX structure


## -description


The <b>NDIS_SYSTEM_PROCESSOR_INFO_EX</b> structure specifies information about the CPU topology of the local
  computer.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_SYSTEM_PROCESSOR_INFO_EX structure. NDIS sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_SYSTEM_PROCESSOR_INFO_EX_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_SYSTEM_PROCESSOR_INFO_EX_REVISION_1.


### -field Flags

Reserved. NDIS sets this member to zero.


### -field ProcessorVendor

The processor vendor specified as one of the values from the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_processor_vendor">
     NDIS_PROCESSOR_VENDOR</a> enumeration.


### -field NumSockets

The total number of processor physical packages (that is, sockets on the local computer
     motherboard) that are in the local computer.


### -field NumCores

The total number of core processors that are in the local computer. For example, set this member
     to four if there are two dual core physical packages.


### -field NumCoresPerSocket

The number of core processors that are in each physical package. For example, set this member to
     two for a dual core physical package.


### -field MaxHyperThreadingProcsPerCore

The maximum number of logical processors that are in each hyper-threaded core processor. For
     example, set this member to two if each hyper-threaded core processor supports two logical
     processors.


### -field ProcessorInfoOffset

The offset, in bytes, from the start of the structure to an array of 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_processor_info_ex">NDIS_PROCESSOR_INFO_EX</a> structures,
     with each entry describing a processor on the computer. The 
     <b>NumberOfProcessors</b> member contains the number of NDIS_PROCESSOR_INFO_EX structures in the array.
     The 
     <b>ProcessorInfoEntrySize</b> member contains the size of the NDIS_PROCESSOR_INFO_EX structures in the
     array.


### -field NumberOfProcessors

The number of elements in the array of NDIS_PROCESSOR_INFO_EX structures that follows this
     structure.


### -field ProcessorInfoEntrySize

The size, in bytes, of elements in the array of NDIS_PROCESSOR_INFO_EX structures that follows
     this structure.


## -remarks



NDIS network drivers use the NDIS_SYSTEM_PROCESSOR_INFO_EX structure in calls to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisgetprocessorinformationex">
    NdisGetProcessorInformationEx</a> function. After 
    <b>NdisGetProcessorInformationEx</b> returns, this structure contains information about the CPU topology
    of the system.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_processor_info_ex">NDIS_PROCESSOR_INFO_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ne-ntddndis-_ndis_processor_vendor">NDIS_PROCESSOR_VENDOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_system_processor_info">NDIS_SYSTEM_PROCESSOR_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisgetprocessorinformationex">
   NdisGetProcessorInformationEx</a>
 

 

