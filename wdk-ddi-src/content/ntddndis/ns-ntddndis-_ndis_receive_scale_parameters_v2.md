---
UID: NS:ntddndis._NDIS_RECEIVE_SCALE_PARAMETERS_V2
title: "_NDIS_RECEIVE_SCALE_PARAMETERS_V2"
description: The NDIS_RECEIVE_SCALE_PARAMETERS_V2 structure specifies the Receive Side Scaling (RSS) parameters for a miniport adapter that advertises support for RSS Version 2 (RSSv2). It is used in the OID_GEN_RECEIVE_SCALE_PARAMETERS_V2 RSSv2 OID.
old-location: netvista\ndis_receive_scale_parameters_v2.htm
tech.root: netvista
ms.assetid: 96EAB6EE-BF9A-46AD-8DED-5D9BD2B6F219
ms.date: 05/02/2018
ms.keywords: "*PNDIS_RECEIVE_SCALE_PARAMETERS_V2, NDIS_RECEIVE_SCALE_PARAMETERS_V2, NDIS_RECEIVE_SCALE_PARAMETERS_V2 structure [Network Drivers Starting with Windows Vista], NDIS_RECEIVE_SCALE_PARAM_ENABLE_RSS, NDIS_RECEIVE_SCALE_PARAM_HASH_INFO_CHANGED, NDIS_RECEIVE_SCALE_PARAM_HASH_KEY_CHANGED, NDIS_RECEIVE_SCALE_PARAM_NUMBER_OF_ENTRIES_CHANGED, NDIS_RECEIVE_SCALE_PARAM_NUMBER_OF_QUEUES_CHANGED, PNDIS_RECEIVE_SCALE_PARAMETERS_V2, PNDIS_RECEIVE_SCALE_PARAMETERS_V2 structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_SCALE_PARAMETERS_V2, netvista.ndis_receive_scale_parameters_v2, ntddndis/NDIS_RECEIVE_SCALE_PARAMETERS_V2, ntddndis/PNDIS_RECEIVE_SCALE_PARAMETERS_V2"
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.80 and later.
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
-	Ntddndis.h
api_name:
-	NDIS_RECEIVE_SCALE_PARAMETERS_V2
product:
- Windows
targetos: Windows
req.typenames: NDIS_RECEIVE_SCALE_PARAMETERS_V2, *PNDIS_RECEIVE_SCALE_PARAMETERS_V2
---

# _NDIS_RECEIVE_SCALE_PARAMETERS_V2 structure


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> RSSv2 is preview only in Windows 10, version 1803.

The **NDIS_RECEIVE_SCALE_PARAMETERS_V2** structure specifies the Receive Side Scaling (RSS) parameters for a miniport adapter that advertises support for <a href="https://docs.microsoft.com/windows-hardware/drivers/network/receive-side-scaling-version-2-rssv2-">RSS Version 2 (RSSv2)</a>. It is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-receive-scale-parameters-v2">OID_GEN_RECEIVE_SCALE_PARAMETERS_V2</a> OID.


## -struct-fields

### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_RECEIVE_SCALE_PARAMETERS_V2</b> structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to <b>NDIS_OBJECT_TYPE_RSS_PARAMETERS_V2</b>. 

For NDIS  6.80 and later drivers, set the 
     <b>Revision</b> member to <b>NDIS_RECEIVE_SCALE_PARAMETERS_V2_REVISION_1</b> and the 
     <b>Size</b> member to <b>sizeof(NDIS_RECEIVE_SCALE_PARAMETERS_V2)</b>.


### -field Flags

A <b>ULONG</b> value that indicates which parameters are being changed. The driver can use these flags to quickly determine which parameters have changed and update the RSS settings accordingly.      

In a query request, set this member to zero.

In a set request, the flags are defined as follows:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NDIS_RECEIVE_SCALE_PARAM_ENABLE_RSS"></a><a id="ndis_receive_scale_param_enable_rss"></a><dl>
<dt><b>NDIS_RECEIVE_SCALE_PARAM_ENABLE_RSS</b></dt>
</dl>
</td>
<td width="60%">
A value of <b>1</b> indicates that RSS is enabled for the specified object. The miniport driver needs to look at other parameters.

A value of <b>0</b> indicates that RSS is disabled for the specified object. The <b>NumberOfQueues</b> and **NumberOfIndirectionTableEntries** parameters can change when RSS is disabled. Other parameters like **HashInformation** and **HashKey** should be ignored when RSS is disabled.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_RECEIVE_SCALE_PARAM_HASH_INFO_CHANGED"></a><a id="ndis_receive_scale_param_hash_info_changed"></a><dl>
<dt><b>NDIS_RECEIVE_SCALE_PARAM_HASH_INFO_CHANGED</b></dt>
</dl>
</td>
<td width="60%">
The value of the <b>HashInformation</b> parameter has changed.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_RECEIVE_SCALE_PARAM_HASH_KEY_CHANGED"></a><a id="ndis_receive_scale_param_hash_key_changed"></a><dl>
<dt><b>NDIS_RECEIVE_SCALE_PARAM_HASH_KEY_CHANGED</b></dt>
</dl>
</td>
<td width="60%">
The contents of the <b>HashSecretKey</b> member have changed.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_RECEIVE_SCALE_PARAM_NUMBER_OF_QUEUES_CHANGED"></a><a id="ndis_receive_scale_param_number_of_queues_changed"></a><dl>
<dt><b>NDIS_RECEIVE_SCALE_PARAM_NUMBER_OF_QUEUES_CHANGED</b></dt>
</dl>
</td>
<td width="60%">
The number of queues per VPort has changed.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_RECEIVE_SCALE_PARAM_NUMBER_OF_ENTRIES_CHANGED"></a><a id="ndis_receive_scale_param_number_of_entries_changed"></a><dl>
<dt><b>NDIS_RECEIVE_SCALE_PARAM_NUMBER_OF_ENTRIES_CHANGED</b></dt>
</dl>
</td>
<td width="60%">
The number of entries in the indirection table has changed.

</td>
</tr>
</table>
 


### -field HashInformation

In a set request, this member is the hash type and hash function that the NIC should use to compute the hash
     values for the incoming packets. If the hash function that is specified within the 
     <b>HashInformation</b> member is zero, RSS is disabled.
     

In a query request, this member is the hash type and hash function that the NIC is using.

Overlying drivers and NDIS can use the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff567266">NDIS_RSS_HASH_INFO_FROM_TYPE_AND_FUNC</a> macro to combine the hash type and hash function into hash
     information and set the 
     <b>HashInformation</b> member.

Miniport drivers can use the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff567266">NDIS_RSS_HASH_TYPE_FROM_HASH_INFO</a> macro to get the hash type from 
     <b>HashInformation</b> and the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff567266">NDIS_RSS_HASH_FUNC_FROM_HASH_INFO</a> macro to get the hash function.

This parameter can be changed at the same time that RSS is enabled, or afterward.


### -field HashSecretKeySize

The size of the secret key array of the hash function, in bytes. The size of the array is 40 bytes for **NdisHashFunctionToeplitz**.

This parameter can be changed at the same time that RSS is enabled, or afterward.


### -field HashSecretKeyOffset

The offset, in bytes, of the hash secret key.

This parameter can be changed at the same time that RSS is enabled, or afterward.

### -field NumberOfQueues

The maximum number of queues for the scaling entity. This parameter is an alias for the NUM_QUEUE_PAIRS variable of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451597">NDIS_NIC_SWITCH_VPORT_PARAMETERS</a> structure, which can also be queried or set through the <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-nic-switch-vport-parameters">OID_NIC_SWITCH_VPORT_PARAMETERS</a> OID. It can be changed when RSS is enabled or disabled.


### -field NumberOfIndirectionTableEntries

The number of indirection table entries (ITEs) for the scaling entity. This value is a power of two and does not exceed the corresponding adapter's capabilities. It can be changed at the before RSS is enabled, or afterward.

New values for this parameter are also a power of two and do exceed adapter capabilities. When this number is increased, the miniport driver should clone the current indirection table into the new ITEs as many times as needed (this is possible because of the power-of-two restriction). When this number is decreased, the upper layer guarantees that the portion of the indirection table which is being removed contains exact replicas of the remaining portion.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451597">NDIS_NIC_SWITCH_VPORT_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567266">NDIS_RSS_HASH_FUNC_FROM_HASH_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567266">NDIS_RSS_HASH_INFO_FROM_TYPE_AND_FUNC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567266">NDIS_RSS_HASH_TYPE_FROM_HASH_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-receive-scale-parameters-v2">OID_GEN_RECEIVE_SCALE_PARAMETERS_V2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-nic-switch-vport-parameters">OID_NIC_SWITCH_VPORT_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/receive-side-scaling-version-2-rssv2-">RSS Version 2 (RSSv2)</a>
 

 

