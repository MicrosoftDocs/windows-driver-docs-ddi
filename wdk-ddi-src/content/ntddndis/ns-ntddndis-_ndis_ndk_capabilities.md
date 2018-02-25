---
UID: NS:ntddndis._NDIS_NDK_CAPABILITIES
title: "_NDIS_NDK_CAPABILITIES"
author: windows-driver-content
description: The NDIS_NDK_CAPABILITIES structure specifies the capabilities of an NDK adapter.
old-location: netvista\ndis_ndk_capabilities.htm
old-project: netvista
ms.assetid: 4E8AD6FA-BB89-4CB0-A06E-7B4917390311
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PNDIS_NDK_CAPABILITIES, ,, A, B, C, D, E, I, K, L, N, NDIS_NDK_CAPABILITIES, NDIS_NDK_CAPABILITIES structure [Network Drivers Starting with Windows Vista], P, PNDIS_NDK_CAPABILITIES, PNDIS_NDK_CAPABILITIES structure pointer [Network Drivers Starting with Windows Vista], S, T, _, _NDIS_NDK_CAPABILITIES, netvista.ndis_ndk_capabilities, ntddndis/NDIS_NDK_CAPABILITIES, ntddndis/PNDIS_NDK_CAPABILITIES"
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
-	NDIS_NDK_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: NDIS_NDK_CAPABILITIES, *PNDIS_NDK_CAPABILITIES
---

# _NDIS_NDK_CAPABILITIES structure


## -description


The <b>NDIS_NDK_CAPABILITIES</b> structure specifies the capabilities of an NDK adapter.


## -syntax


````
typedef struct _NDIS_NDK_CAPABILITIES {
  NDIS_OBJECT_HEADER Header;
  ULONG              MaxQpCount;
  ULONG              MaxCqCount;
  ULONG              MaxMrCount;
  ULONG              MaxPdCount;
  ULONG              MaxInboundReadLimit;
  ULONG              MaxOutboundReadLimit;
  ULONG              MaxMwCount;
  ULONG              MaxSrqCount;
  ULONG64            MissingCounterMask;
  NDK_ADAPTER_INFO   *NdkInfo;
} NDIS_NDK_CAPABILITIES, *PNDIS_NDK_CAPABILITIES;
````


## -struct-fields




### -field Header

The <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure that describes this <b>NDIS_NDK_CAPABILITIES</b> structure. Set the members of the <b>NDIS_OBJECT_HEADER</b> structure as follows:

<ul>
<li>Set the <b>Type</b> member to <b>NDIS_OBJECT_TYPE_DEFAULT</b>.</li>
<li>Set the <b>Revision</b> member to <b>NDIS_NDK_CAPABILITIES_REVISION_1</b>.</li>
<li>Set the <b>Size</b> member to <b>NDIS_SIZEOF_NDK_CAPABILITIES_REVISION_1</b>.</li>
</ul>

### -field Flags

 


### -field MaxQpCount

The maximum number of queue pairs (QPs) that can be supported by the adapter.


### -field MaxCqCount

The maximum number of completion queues (CQs) that can be supported by the adapter.


### -field MaxMrCount

The maximum number of memory regions (MRs) that can be supported by the adapter.


### -field MaxPdCount

The maximum number of protection domains (PDs) that can be supported by the adapter


### -field MaxInboundReadLimit

The maximum number of incoming outstanding read requests that can be supported by the adapter. 
     If this member is zero, there is no adapter limit. In this case, there is still a limit for each queue pair. The limit for each queue pair is specified in the <b>MaxInboundReadLimit</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a> structure.


### -field MaxOutboundReadLimit

The maximum number of outgoing outstanding read requests that can be supported by the adapter. 
    If this member is zero, there is no adapter-wide limit.  In this case, there is still a limit for each queue pair. The limit for each queue pair is specified in the <b>MaxOutboundReadLimit</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a> structure.


### -field MaxMwCount

The maximum number of memory windows (MWs) that are supported by the adapter.


### -field MaxSrqCount

The maximum number of shared receive queues (SRQs) that are supported by the adapter.


### -field MissingCounterMask

A bitmask that identifies counters that an NDK provider does not support. NDK providers are required to support all the performance counters that are included
    in the <a href="..\ntddndis\ns-ntddndis-_ndis_ndk_performance_counters.md">NDIS_NDK_PERFORMANCE_COUNTERS</a> structure. However, in the rare case that
    a provider cannot support a counter due to extreme implementation difficulties,
    the provider must indicate any unsupported counters with the mask value for the
    counter which it cannot support.


### -field NdkInfo

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a> structure that specifies NDK adapter capabilities and limits that are relevant for an specific NDK consumer. These capabilities can be different from system-wide limits.


## -remarks



<b>NDIS_NDK_CAPABILITIES</b> specifies capacity limits that are relevant for
    system-wide management or partitioning of resources that are available on a given NDK adapter.

Independent of whether NDK functionality of an adapter is currently enabled or disabled,
    an NDK-capable adapter must always indicate its capabilities during miniport initialization.


The <b>NDIS_NDK_CAPABILITIES</b> structure is used in the <a href="..\ndis\ns-ndis-_ndis_miniport_adapter_ndk_attributes.md">NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES</a> structure.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_ndk_performance_counters.md">NDIS_NDK_PERFORMANCE_COUNTERS</a>



<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_ndk_attributes.md">NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_NDK_CAPABILITIES structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

