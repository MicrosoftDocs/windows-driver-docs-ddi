---
UID: NS:ntddndis._NDIS_SYSTEM_PROCESSOR_INFO_EX
title: "_NDIS_SYSTEM_PROCESSOR_INFO_EX"
author: windows-driver-content
description: The NDIS_SYSTEM_PROCESSOR_INFO_EX structure specifies information about the CPU topology of the local computer.
old-location: netvista\ndis_system_processor_info_ex.htm
old-project: netvista
ms.assetid: ba3c6641-98bc-4c44-9889-7583c4cf61f0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNDIS_SYSTEM_PROCESSOR_INFO_EX, NDIS_SYSTEM_PROCESSOR_INFO_EX, NDIS_SYSTEM_PROCESSOR_INFO_EX structure [Network Drivers Starting with Windows Vista], PNDIS_SYSTEM_PROCESSOR_INFO_EX, PNDIS_SYSTEM_PROCESSOR_INFO_EX structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SYSTEM_PROCESSOR_INFO_EX, ndis_processor_group_ref_754737d7-8279-4786-b89d-4326da949464.xml, netvista.ndis_system_processor_info_ex, ntddndis/NDIS_SYSTEM_PROCESSOR_INFO_EX, ntddndis/PNDIS_SYSTEM_PROCESSOR_INFO_EX"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddndis.h
api_name:
-	NDIS_SYSTEM_PROCESSOR_INFO_EX
product: Windows
targetos: Windows
req.typenames: NDIS_SYSTEM_PROCESSOR_INFO_EX, *PNDIS_SYSTEM_PROCESSOR_INFO_EX
---

# _NDIS_SYSTEM_PROCESSOR_INFO_EX structure


## -description


The <b>NDIS_SYSTEM_PROCESSOR_INFO_EX</b> structure specifies information about the CPU topology of the local
  computer.


## -syntax


````
typedef struct _NDIS_SYSTEM_PROCESSOR_INFO_EX {
  NDIS_OBJECT_HEADER    Header;
  ULONG                 Flags;
  NDIS_PROCESSOR_VENDOR ProcessorVendor;
  ULONG                 NumSockets;
  ULONG                 NumCores;
  ULONG                 NumCoresPerSocket;
  ULONG                 MaxHyperThreadingProcsPerCore;
  ULONG                 ProcessorInfoOffset;
  ULONG                 NumberOfProcessors;
  ULONG                 ProcessorInfoEntrySize;
} NDIS_SYSTEM_PROCESSOR_INFO_EX, *PNDIS_SYSTEM_PROCESSOR_INFO_EX;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_SYSTEM_PROCESSOR_INFO_EX structure. NDIS sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_SYSTEM_PROCESSOR_INFO_EX_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_SYSTEM_PROCESSOR_INFO_EX_REVISION_1.


### -field Flags

Reserved. NDIS sets this member to zero.


### -field ProcessorVendor

The processor vendor specified as one of the values from the 
     <a href="..\ntddndis\ne-ntddndis-_ndis_processor_vendor.md">
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
     <a href="..\ntddndis\ns-ntddndis-_ndis_processor_info_ex.md">NDIS_PROCESSOR_INFO_EX</a> structures,
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
    <a href="..\ndis\nf-ndis-ndisgetprocessorinformationex.md">
    NdisGetProcessorInformationEx</a> function. After 
    <b>NdisGetProcessorInformationEx</b> returns, this structure contains information about the CPU topology
    of the system.




## -see-also

<a href="..\ndis\ns-ndis-_ndis_system_processor_info.md">NDIS_SYSTEM_PROCESSOR_INFO</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_processor_info_ex.md">NDIS_PROCESSOR_INFO_EX</a>



<a href="..\ntddndis\ne-ntddndis-_ndis_processor_vendor.md">NDIS_PROCESSOR_VENDOR</a>



<a href="..\ndis\nf-ndis-ndisgetprocessorinformationex.md">
   NdisGetProcessorInformationEx</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SYSTEM_PROCESSOR_INFO_EX structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

