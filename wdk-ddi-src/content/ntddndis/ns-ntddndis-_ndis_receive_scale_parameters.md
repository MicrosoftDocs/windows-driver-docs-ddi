---
UID: NS:ntddndis._NDIS_RECEIVE_SCALE_PARAMETERS
title: "_NDIS_RECEIVE_SCALE_PARAMETERS"
author: windows-driver-content
description: The NDIS_RECEIVE_SCALE_PARAMETERS structure specifies the receive side scaling (RSS) parameters for a miniport adapter.
old-location: netvista\ndis_receive_scale_parameters.htm
old-project: netvista
ms.assetid: 0d51042e-06b4-4105-889f-84a368e5735a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NDIS_RSS_PARAM_FLAG_HASH_INFO_UNCHANGED, PNDIS_RECEIVE_SCALE_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], receive_scaling_structures_ref_1055bbcb-da8b-4ee1-bd03-55abfa79b5ab.xml, ntddndis/PNDIS_RECEIVE_SCALE_PARAMETERS, PNDIS_RECEIVE_SCALE_PARAMETERS, NDIS_RSS_PARAM_FLAG_ITABLE_UNCHANGED, NDIS_RSS_PARAM_FLAG_BASE_CPU_UNCHANGED, NDIS_RECEIVE_SCALE_PARAMETERS structure [Network Drivers Starting with Windows Vista], NDIS_RECEIVE_SCALE_PARAMETERS, _NDIS_RECEIVE_SCALE_PARAMETERS, ntddndis/NDIS_RECEIVE_SCALE_PARAMETERS, *PNDIS_RECEIVE_SCALE_PARAMETERS, netvista.ndis_receive_scale_parameters, NDIS_RSS_PARAM_FLAG_DISABLE_RSS, NDIS_RSS_PARAM_FLAG_HASH_KEY_UNCHANGED
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddndis.h
apiname:
-	NDIS_RECEIVE_SCALE_PARAMETERS
product: Windows
targetos: Windows
req.typenames: "*PNDIS_RECEIVE_SCALE_PARAMETERS, NDIS_RECEIVE_SCALE_PARAMETERS"
---

# _NDIS_RECEIVE_SCALE_PARAMETERS structure


## -description


The <b>NDIS_RECEIVE_SCALE_PARAMETERS</b> structure specifies the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-receive-side-scaling2">receive side scaling (RSS)</a> parameters for a miniport adapter.
  

<b>Version Information
  </b>


## -syntax


````
typedef struct _NDIS_RECEIVE_SCALE_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  USHORT             Flags;
  USHORT             BaseCpuNumber;
  ULONG              HashInformation;
  USHORT             IndirectionTableSize;
  ULONG              IndirectionTableOffset;
  USHORT             HashSecretKeySize;
  ULONG              HashSecretKeyOffset;
#if NDIS_SUPPORT_NDIS620
  ULONG              ProcessorMasksOffset;
  ULONG              NumberOfProcessorMasks;
  ULONG              ProcessorMasksEntrySize;
#endif 
#if NDIS_SUPPORT_NDIS660
  PROCESSOR_NUMBER   DefaultProcessorNumber;
#endif 
} NDIS_RECEIVE_SCALE_PARAMETERS, *PNDIS_RECEIVE_SCALE_PARAMETERS;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_RECEIVE_SCALE_PARAMETERS</b> structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to <b>NDIS_OBJECT_TYPE_RSS_PARAMETERS</b>. 

For NDIS  6.60 and later drivers, set the 
     <b>Revision</b> member to <b>NDIS_RECEIVE_SCALE_PARAMETERS_REVISION_3</b> and the 
     <b>Size</b> member to <b>NDIS_SIZEOF_RECEIVE_SCALE_PARAMETERS_REVISION_3</b>.

For NDIS  6.20 and later drivers, set the 
     <b>Revision</b> member to <b>NDIS_RECEIVE_SCALE_PARAMETERS_REVISION_2</b> and the 
     <b>Size</b> member to <b>NDIS_SIZEOF_RECEIVE_SCALE_PARAMETERS_REVISION_2</b>.

For NDIS  6.0 drivers, set the 
     <b>Revision</b> member to <b>NDIS_RECEIVE_SCALE_PARAMETERS_REVISION_1</b> and the 
     <b>Size</b> member to <b>NDIS_SIZEOF_RECEIVE_SCALE_PARAMETERS_REVISION_1</b>.


### -field Flags

A <b>USHORT</b> value that indicates what the miniport driver should do with the receive-scale
     parameters. The driver can use these flags to quickly determine which parameters have changed and update
     the RSS settings accordingly. 
     
<div class="alert"><b>Note</b>  The flags which refer to unchanged RSS parameter information are for optimization purposes.  If a flag is set, no change has been made to the corresponding parameter. If a flag is clear, the corresponding parameter may or may not have changed and miniport drivers must compare the new value of the parameter with the current value in order to determine a potential change in the parameter.</div><div> </div>In a query request, set this member to zero.

In a set request, the flags are defined as follows:
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NDIS_RSS_PARAM_FLAG_BASE_CPU_UNCHANGED"></a><a id="ndis_rss_param_flag_base_cpu_unchanged"></a><dl>
<dt><b>NDIS_RSS_PARAM_FLAG_BASE_CPU_UNCHANGED</b></dt>
</dl>
</td>
<td width="60%">
The 
       <b>BaseCpuNumber</b> member has not changed.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_RSS_PARAM_FLAG_HASH_INFO_UNCHANGED"></a><a id="ndis_rss_param_flag_hash_info_unchanged"></a><dl>
<dt><b>NDIS_RSS_PARAM_FLAG_HASH_INFO_UNCHANGED</b></dt>
</dl>
</td>
<td width="60%">
The 
       <b>HashInformation</b> member has not changed. The hash information includes the hash types and hash
       function.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_RSS_PARAM_FLAG_ITABLE_UNCHANGED"></a><a id="ndis_rss_param_flag_itable_unchanged"></a><dl>
<dt><b>NDIS_RSS_PARAM_FLAG_ITABLE_UNCHANGED</b></dt>
</dl>
</td>
<td width="60%">
The indirection table and associated data members have not changed.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_RSS_PARAM_FLAG_HASH_KEY_UNCHANGED"></a><a id="ndis_rss_param_flag_hash_key_unchanged"></a><dl>
<dt><b>NDIS_RSS_PARAM_FLAG_HASH_KEY_UNCHANGED</b></dt>
</dl>
</td>
<td width="60%">
The secret key and associated data members have not changed.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_RSS_PARAM_FLAG_DISABLE_RSS"></a><a id="ndis_rss_param_flag_disable_rss"></a><dl>
<dt><b>NDIS_RSS_PARAM_FLAG_DISABLE_RSS</b></dt>
</dl>
</td>
<td width="60%">
If this flag is set, the miniport driver should ignore all of the other flags and settings and
       disable RSS on the NIC.

</td>
</tr>
</table> 


### -field BaseCpuNumber

The lowest number CPU to use for RSS. Because this value is incorporated into the indirection
     table, set 
     <b>BaseCpuNumber</b> to zero.


### -field HashInformation

In a set request, this member is the hash type and hash function that the NIC should use to compute the hash
     values for the incoming packets. If the hash function that is specified within the 
     <b>HashInformation</b> member is zero, RSS is disabled.
     

In a query request, this member is the hash type and hash function that the NIC is using.

Overlying drivers and NDIS can use the 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff567266">NDIS_RSS_HASH_INFO_FROM_TYPE_AND_FUNC</a> macro to combine the hash type and hash function into hash
     information and set the 
     <b>HashInformation</b> member.

Miniport drivers can use the 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff567266">NDIS_RSS_HASH_TYPE_FROM_HASH_INFO</a> macro to get the hash type from 
     <b>HashInformation</b> and the 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff567266">NDIS_RSS_HASH_FUNC_FROM_HASH_INFO</a> macro to get the hash function.


### -field IndirectionTableSize

The size of the indirection table, in bytes. The upper layer driver that sets the RSS parameters, must ensure that the number of entries in the indirection table is a power of 2.


### -field IndirectionTableOffset

The offset of the indirection table from the beginning of the <b>NDIS_RECEIVE_SCALE_PARAMETERS</b>
     structure. Use this offset to get the indirection table.


### -field HashSecretKeySize

The size of the secret key array of the hash function, in bytes. The size of the array is 40 bytes for NdisHashFunctionToeplitz.


### -field HashSecretKeyOffset

The offset of the secret key array of the hash function from the beginning of the
     <b>NDIS_RECEIVE_SCALE_PARAMETERS</b> structure. Use this offset to get the 320-bit (40 bytes) secret key. 
     

In a set request, the secret key can contain any data that the overlying driver chooses.

In a query request, the secret key contains the data that the NIC is using.


### -field ProcessorMasksOffset

The offset of an array of processor masks from the beginning of the <b>NDIS_RECEIVE_SCALE_PARAMETERS</b>
     structure.


### -field NumberOfProcessorMasks

The number of elements in an array of type <a href="..\miniport\ns-miniport-_group_affinity.md">GROUP_AFFINITY</a> representing the processors used in the indirection table


### -field ProcessorMasksEntrySize

The size, in bytes, of a processor mask array entry.


### -field DefaultProcessorNumber

Specifies the default RSS processor.


## -remarks


The <b>NDIS_RECEIVE_SCALE_PARAMETERS</b> structure defines the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-receive-side-scaling2">receive side scaling (RSS)</a> parameters for the 
    <mshelp:link keywords="netvista.oid_gen_receive_scale_parameters" tabindex="0">
    OID_GEN_RECEIVE_SCALE_PARAMETERS</mshelp:link> OID.
<div class="alert"><b>Note</b>  The indirection table and secret key are appended after the
    <b>NDIS_RECEIVE_SCALE_PARAMETERS</b> structure members.</div><div> </div>For NDIS 6.20 and later versions, the indirection table has the following format:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROCESSOR_NUMBER     IndirectionTable[IndirectionTableSize/sizeof(PROCESSOR_NUMBER)];</pre>
</td>
</tr>
</table></span></div>For drivers earlier than NDIS 6.20, the indirection table has the following format:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>CCHAR     IndirectionTable[IndirectionTableSize];</pre>
</td>
</tr>
</table></span></div>NDIS automatically translates the indirection table if there are older and newer drivers in a driver stack.

The miniport driver must examine the indirection table to determine the CPU numbers to associate with
    hardware queues. If the total number of different CPU numbers that appear in the indirection table is
    more than the number of hardware queues that the NIC supports, the miniport driver must pick a subset of
    the CPU numbers from the indirection table. The subset is equal in number to the number of hardware
    queues.

The miniport driver specified the number of receive queues value in response to 
    <mshelp:link keywords="netvista.oid_gen_receive_scale_capabilities" tabindex="0">
    OID_GEN_RECEIVE_SCALE_CAPABILITIES</mshelp:link>.

To clear the RSS parameters and disable RSS, NDIS sets the hash function that is specified
    within the 
    <b>HashInformation</b> member is zero. NDIS can also disable RSS by setting the
    <b>NDIS_RSS_PARAM_FLAG_DISABLE_RSS</b> flag in the <b>NDIS_RECEIVE_SCALE_PARAMETERS</b> structure.

If RSS is disabled, the miniport driver should handle receive operations without performing RSS
    operations.



## -see-also

<mshelp:link keywords="netvista.ndis_rss_hash_func_from_hash_info" tabindex="0"><b>
   NDIS_RSS_HASH_FUNC_FROM_HASH_INFO</b></mshelp:link>

<mshelp:link keywords="netvista.ndis_rss_hash_type_from_hash_info" tabindex="0"><b>
   NDIS_RSS_HASH_TYPE_FROM_HASH_INFO</b></mshelp:link>

<mshelp:link keywords="netvista.ndis_rss_hash_info_from_type_and_func" tabindex="0"><b>
   NDIS_RSS_HASH_INFO_FROM_TYPE_AND_FUNC</b></mshelp:link>

<mshelp:link keywords="netvista.oid_gen_receive_scale_parameters" tabindex="0">
   OID_GEN_RECEIVE_SCALE_PARAMETERS</mshelp:link>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-receive-side-scaling2">Receive Side Scaling (RSS)</a>

<mshelp:link keywords="netvista.oid_gen_receive_scale_capabilities" tabindex="0">
   OID_GEN_RECEIVE_SCALE_CAPABILITIES</mshelp:link>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RECEIVE_SCALE_PARAMETERS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

