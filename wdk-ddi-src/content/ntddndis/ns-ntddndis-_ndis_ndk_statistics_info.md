---
UID: NS:ntddndis._NDIS_NDK_STATISTICS_INFO
title: "_NDIS_NDK_STATISTICS_INFO"
author: windows-driver-content
description: The NDIS_NDK_STATISTICS_INFO structure contains the NDK statistics.
old-location: netvista\ndis_ndk_statistics_info.htm
old-project: netvista
ms.assetid: F3FA3790-0754-4D5E-9F27-8ECD71278520
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndis_ndk_statistics_info, ntddndis/PNDIS_NDK_STATISTICS_INFO, NDIS_NDK_STATISTICS_INFO, ntddndis/NDIS_NDK_STATISTICS_INFO, NDIS_NDK_STATISTICS_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_NDK_STATISTICS_INFO structure pointer [Network Drivers Starting with Windows Vista], PNDIS_NDK_STATISTICS_INFO, _NDIS_NDK_STATISTICS_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
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
-	ntddndis.h
apiname:
-	NDIS_NDK_STATISTICS_INFO
product: Windows
targetos: Windows
req.typenames: NDIS_NDK_STATISTICS_INFO
---

# _NDIS_NDK_STATISTICS_INFO structure


## -description


The <b>NDIS_NDK_STATISTICS_INFO</b> structure contains the NDK statistics.


## -syntax


````
typedef struct _NDIS_NDK_STATISTICS_INFO {
  NDIS_OBJECT_HEADER            Header;
  NDIS_NDK_PERFORMANCE_COUNTERS CounterSet;
} NDIS_NDK_STATISTICS_INFO, *PNDIS_NDK_STATISTICS_INFO;
````


## -struct-fields




### -field Header

An <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure that describes this <b>NDIS_NDK_STATISTICS_INFO</b> structure. Set the members of the <b>NDIS_OBJECT_HEADER</b> structure as follows:
<ul>
<li>Set the <b>Type</b> member to <b>NDIS_OBJECT_TYPE_DEFAULT</b>.</li>
<li>Set the <b>Revision</b> member to <b>NDIS_NDK_STATISTICS_INFO_REVISION_1</b>.</li>
<li>Set the <b>Size</b> member to <b>NDIS_SIZEOF_NDK_STATISTICS_INFO_REVISION_1</b>.</li>
</ul>

### -field Flags

 


### -field CounterSet

An <a href="..\ntddndis\ns-ntddndis-_ndis_ndk_performance_counters.md">NDIS_NDK_PERFORMANCE_COUNTERS</a> structure that contains the NDK performance counters.


## -remarks


The <b>NDIS_NDK_STATISTICS_INFO</b> structure is returned with the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451813">OID_NDK_STATISTICS</a> OID. The <b>InformationBuffer</b> member of the <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure contains a pointer to this structure.



The NDK-capable miniport driver is required to fill in the <b>CounterSet</b> member, which is an <a href="..\ntddndis\ns-ntddndis-_ndis_ndk_performance_counters.md">NDIS_NDK_PERFORMANCE_COUNTERS</a> structure.



## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_ndk_performance_counters.md">NDIS_NDK_PERFORMANCE_COUNTERS</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451813">OID_NDK_STATISTICS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_NDK_STATISTICS_INFO structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

