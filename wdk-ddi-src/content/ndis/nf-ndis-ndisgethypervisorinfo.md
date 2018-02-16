---
UID: NF:ndis.NdisGetHypervisorInfo
title: NdisGetHypervisorInfo function
author: windows-driver-content
description: Important  Starting with Windows 10 Version 1703, NdisGetHypervisorInfo is deprecated and should not be used.
old-location: netvista\ndisgethypervisorinfo.htm
old-project: netvista
ms.assetid: 5469c6aa-90df-4379-b670-23aaa6919055
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndisgethypervisorinfo, virtual_machine_queue_ref_afe96cc4-b307-4953-9587-65b6bec35b18.xml, NdisGetHypervisorInfo, ndis/NdisGetHypervisorInfo, NdisGetHypervisorInfo function [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisGetHypervisorInfo
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisGetHypervisorInfo function


## -description


<div class="alert"><b>Important</b>  <p class="note">Starting with Windows 10 Version 1703, NdisGetHypervisorInfo is deprecated and should not be used.  Drivers are encouraged to move away from it, as it may not be available in future versions of the operating system. 

<p class="note">Drivers should instead follow a hypervisor's instructions to query hypervisor presence and capabilities. For example, Hyper-V's instructions are documented in the <a href="https://docs.microsoft.com/virtualization/hyper-v-on-windows/reference/tlfs">Top-Level Functional Specification</a>.

</div><div> </div>The 
  <b>NdisGetHypervisorInfo</b> function returns information about the 
  hypervisor that is present on the
  system.


## -syntax


````
NDIS_STATUS NdisGetHypervisorInfo(
  _Inout_ PNDIS_HYPERVISOR_INFO HypervisorInfo
);
````


## -parameters




### -param HypervisorInfo [in, out]

A pointer to a caller-allocated <a href="..\ntddndis\ns-ntddndis-_ndis_hypervisor_info.md">NDIS_HYPERVISOR_INFO</a> structure that
     contains information about the hypervisor that is present on the system.


## -returns



<b>NdisGetHypervisorInfo</b> can return one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BUFFER_TOO_SHORT</b></dt>
</dl>
</td>
<td width="60%">
The size of the input parameter buffer was too small.

</td>
</tr>
</table>
 




## -remarks



NDIS miniport drivers call the 
    <b>NdisGetHypervisorInfo</b> function to determine whether a hypervisor is present on the system.

When the <b>NdisGetHypervisorInfo</b> function returns, the <i>HypervisorInfo</i> parameter contains a pointer to an <a href="..\ntddndis\ns-ntddndis-_ndis_hypervisor_info.md">NDIS_HYPERVISOR_INFO</a> structure. This structure contains information about whether a hypervisor is present, along with the partition type from which this function was called. The <b>NDIS_HYPERVISOR_INFO</b> structure provides this information in the following way:

<ul>
<li>
If a hypervisor is present, the <b>NDIS_HYPERVISOR_INFO_FLAG_HYPERVISOR_PRESENT</b> 
flag is set in the <b>Flags</b> member.

</li>
<li>
If the Microsoft hypervisor is present, the <b>PartitionType</b> member is set to one of the following values: 

<ul>
<li>
If the <b>NdisGetHypervisorInfo</b> function was called from the management operating system that runs in the Hyper-V parent partition, the <b>PartitionType</b> member is set to <b>NdisHypervisorPartitionTypeMsHvParent</b>.

</li>
<li>
If the <b>NdisGetHypervisorInfo</b> function was called from the guest operating system that runs in the Hyper-V child partition, the <b>PartitionType</b> member is set to <b>NdisHypervisorPartitionMsHvChild</b>.

</li>
</ul>
</li>
<li>
If another vendor's hypervisor is present, the <b>PartitionType</b> member is set to  <b>NdisHypervisorPartitionTypeUnknown</b>.

</li>
</ul>
<div class="alert"><b>Note</b>  A driver must initialize the 
    <b>Header</b> member of the <a href="..\ntddndis\ns-ntddndis-_ndis_hypervisor_info.md">NDIS_HYPERVISOR_INFO</a> structure before it calls the <b>NdisGetHypervisorInfo</b> function.</div>
<div> </div>



## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_hypervisor_info.md">NDIS_HYPERVISOR_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisGetHypervisorInfo function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

