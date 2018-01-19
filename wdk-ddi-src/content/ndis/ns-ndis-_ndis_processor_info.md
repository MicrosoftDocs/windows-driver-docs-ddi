---
UID: NS:ndis._NDIS_PROCESSOR_INFO
title: _NDIS_PROCESSOR_INFO
author: windows-driver-content
description: The NDIS_PROCESSOR_INFO structure specifies information about a processor in the local computer.
old-location: netvista\ndis_processor_info.htm
old-project: netvista
ms.assetid: 55c7044e-20db-4245-a644-93cbeb9cd512
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_PROCESSOR_INFO, NDIS_PROCESSOR_INFO, *PNDIS_PROCESSOR_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and 6.1. For NDIS 6.20 and later, use NDIS_PROCESSOR_INFO_EX.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_PROCESSOR_INFO
req.alt-loc: ndis.h
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
req.typenames: NDIS_PROCESSOR_INFO, *PNDIS_PROCESSOR_INFO
---

# _NDIS_PROCESSOR_INFO structure



## -description
The <b>NDIS_PROCESSOR_INFO</b> structure specifies information about a processor in the local
  computer.



## -syntax

````
typedef struct _NDIS_PROCESSOR_INFO {
  ULONG CpuNumber;
  ULONG PhysicalPackageId;
  ULONG CoreId;
  ULONG HyperThreadID;
} NDIS_PROCESSOR_INFO, *PNDIS_PROCESSOR_INFO;
````


## -struct-fields

### -field CpuNumber

The CPU number that is assigned to the processor. The value is in the range from zero through the
     number of active CPUs minus one.


### -field PhysicalPackageId

The physical package ID of the processor. The value is in the range from zero through the number
     in the 
     <b>NumPhysicalPackages</b> member of the 
     <a href="..\ndis\ns-ndis-_ndis_system_processor_info.md">
     NDIS_SYSTEM_PROCESSOR_INFO</a> structure minus one.


### -field CoreId

The core ID of the processor. The value is in the range from zero through the number in the 
     <b>NumCoresPerPhysicalPackage</b> member of the NDIS_SYSTEM_PROCESSOR_INFO structure minus one.


### -field HyperThreadID

The hyper-threading ID of the processor. The value is in the range from zero through the number in
     the 
     <b>MaxHyperThreadingCpusPerCore</b> member of the NDIS_SYSTEM_PROCESSOR_INFO structure minus one.


## -remarks
The NDIS_PROCESSOR_INFO structure is used in the 
    <a href="..\ndis\ns-ndis-_ndis_system_processor_info.md">
    NDIS_SYSTEM_PROCESSOR_INFO</a> structure.


## -see-also
<dl>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_processor_info_ex.md">NDIS_PROCESSOR_INFO_EX</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_system_processor_info.md">NDIS_SYSTEM_PROCESSOR_INFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PROCESSOR_INFO structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

