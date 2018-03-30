---
UID: NC:ndis.NDIS_SWITCH_REPORT_FILTERED_NET_BUFFER_LISTS
title: NDIS_SWITCH_REPORT_FILTERED_NET_BUFFER_LISTS
author: windows-driver-content
description: The ReportFilteredNetBufferLists function reports on one or more network packets that were dropped or excluded from port delivery by the extensible switch extension. Each network packet is defined through a NET_BUFFER_LIST structure.
old-location: netvista\reportfilterednetbufferlists.htm
old-project: netvista
ms.assetid: 06E7FC94-628D-4601-8173-F118043A13FB
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NDIS_SWITCH_REPORT_FILTERED_NET_BUFFER_LISTS, ReportFilteredNetBufferLists, ReportFilteredNetBufferLists callback function [Network Drivers Starting with Windows Vista], ndis/ReportFilteredNetBufferLists, netvista.reportfilterednetbufferlists
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	ReportFilteredNetBufferLists
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# NDIS_SWITCH_REPORT_FILTERED_NET_BUFFER_LISTS callback


## -description



The <i>ReportFilteredNetBufferLists</i> function reports on one or more network packets that were dropped or excluded from port delivery by the extensible switch extension. Each network packet is defined through a <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure.






## -parameters




### -param NdisSwitchContext [in]

An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the extension calls <a href="https://msdn.microsoft.com/library/windows/hardware/hh598204">NdisFGetOptionalSwitchHandlers</a>,  this handle is returned through the <i>NdisSwitchContext</i> parameter.


### -param ExtensionGuid [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that contains the GUID of the extension. NDIS specifies this GUID in the <b>FilterModuleGuidName</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565481">NDIS_FILTER_ATTACH_PARAMETERS</a> structure. NDIS passes a pointer to this structure in the <i>AttachParameters</i> parameter when it calls the extension's <a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a> function.


### -param ExtensionFriendlyName [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that contains the user-friendly name of the extension. This name is defined by the <b>DisplayName</b>     entry in the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/install/inf-addservice-directive">AddService Directive</a>
of the extension's INF file.


### -param PortId [in]

An NDIS_SWITCH_PORT_ID value that specifies an extensible switch port. For more information, see the Remarks section.


### -param Flags [in]

A UINT32 value. When the NDIS_SWITCH_REPORT_FILTERED_NBL_FLAGS_IS_INCOMING flag is specified, it indicates that the <b>PortId</b> member defines the source of the dropped packet. When it is not specified, the PortId member defines the destination extensible switch port. For more information, see the Remarks section.


### -param NumberOfNetBufferLists [in]

A UINT32 value that contains the number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures that is specified by the <i>NetBufferLists</i> parameter.


### -param NetBufferLists [in]

A pointer to a linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures. 


### -param FilterReason [in, optional]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that contains a user-friendly description of the reason for the drop or exclusion of the packets. For more information, see the Remarks section.


## -returns



This callback function does not return a value.




## -remarks



When the extension excludes the delivery of a packet to an extensible switch port, it must call <i>ReportFilteredNetBufferLists</i>. When this function is called, the extensible switch module increments counters and logs events for the dropped or excluded packets. When it logs an event for a dropped or excluded set of packets, the extensible switch module uses the user-friendly description that is specified by the <i>FilterReason</i> parameter.

The extension can exclude the delivery of a packet in the following ways:

<ul>
<li>
The extension completes the packet instead of forwarding it on through the extensible switch driver stack. For example, the extension can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff562618">NdisFSendNetBufferListsComplete</a> to drop a packet that it inspected when NDIS calls its <a href="https://msdn.microsoft.com/1b3fc0c8-95da-47e5-8ff1-b7967f5148e7">FilterSendNetBufferLists</a> function. 

</li>
<li>
 The extension changes the destination ports for a packet. For example, the extension must call <i>ReportFilteredNetBufferLists</i> if it sets the <b>IsExcluded</b> member to <b>TRUE</b> in the  <a href="https://msdn.microsoft.com/library/windows/hardware/hh598224">NDIS_SWITCH_PORT_DESTINATION</a> structure for a destination port of the packet. 

For more information on how to exclude packet delivery to extensible switch ports, see <a href="https://msdn.microsoft.com/04BF02A6-360F-482E-A86B-31232AFCB778">Excluding Packet Delivery to Extensible Switch Destination Ports</a>.

</li>
</ul>
The extension must follow these guidelines when it calls <i>ReportFilteredNetBufferLists</i>:

<ul>
<li>
The <i>NetBufferLists</i> parameter specified a linked-list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures. All of the packets specified by these structures must have been received from or sent to the same port, and were dropped or excluded for the same reason. 

</li>
<li>
If the packet is being dropped due to policy based on the source port, the NDIS_SWITCH_REPORT_FILTERED_NBL_FLAGS_IS_INCOMING flag must be specified.  The extension must also set the <i>PortId</i> parameter to the identifier of the port from which the packet was received.

</li>
<li>
If the packet is being dropped due to policy based on the destination port, the NDIS_SWITCH_REPORT_FILTERED_NBL_FLAGS_IS_INCOMING flag must not be specified.  The extension must also set the <i>PortId</i> parameter to the identifier of the port to which the packet was to be sent.

</li>
</ul>



## -see-also




<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/install/inf-addservice-directive">INF AddService Directive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565481">NDIS_FILTER_ATTACH_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598224">NDIS_SWITCH_PORT_DESTINATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598204">NdisFGetOptionalSwitchHandlers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_REPORT_FILTERED_NET_BUFFER_LISTS callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
