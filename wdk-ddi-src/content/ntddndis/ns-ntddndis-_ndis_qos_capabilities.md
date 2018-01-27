---
UID: NS:ntddndis._NDIS_QOS_CAPABILITIES
title: _NDIS_QOS_CAPABILITIES
author: windows-driver-content
description: The NDIS_QOS_CAPABILITIES structure specifies the NDIS Quality of Service (QoS) capabilities of a network adapter that supports the IEEE 802.1 Data Center Bridging (DCB) interface.
old-location: netvista\ndis_qos_capabilities.htm
old-project: netvista
ms.assetid: 23698bb8-3fb6-4e60-aaac-75c2e3341d54
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PNDIS_QOS_CAPABILITIES structure pointer [Network Drivers Starting with Windows Vista], NDIS_QOS_CAPABILITIES structure [Network Drivers Starting with Windows Vista], netvista.ndis_qos_capabilities, _NDIS_QOS_CAPABILITIES, ntddndis/PNDIS_QOS_CAPABILITIES, NDIS_QOS_CAPABILITIES, ntddndis/NDIS_QOS_CAPABILITIES, PNDIS_QOS_CAPABILITIES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
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
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Ntddndis.h
apiname: 
-	NDIS_QOS_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: PNDIS_QOS_CAPABILITIES, NDIS_QOS_CAPABILITIES
---

# _NDIS_QOS_CAPABILITIES structure


## -description



The <b>NDIS_QOS_CAPABILITIES</b> structure specifies the NDIS Quality of Service (QoS) capabilities of a network adapter that supports the IEEE 802.1 Data Center Bridging (DCB) interface.




## -syntax


````
typedef struct _NDIS_QOS_CAPABILITIES {
  NDIS_OBJECT_HEADER Header;
  ULONG              Flags;
  ULONG              MaxNumTrafficClasses;
  ULONG              MaxNumEtsCapableTrafficClasses;
  ULONG              MaxNumPfcEnabledTrafficClasses;
} NDIS_QOS_CAPABILITIES, *PNDIS_QOS_CAPABILITIES;
````


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_QOS_CAPABILITIES</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_QOS_CAPABILITIES. To specify the version of the <b>NDIS_QOS_CAPABILITIES</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 




### -field Flags

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags that specify the NDIS QoS capabilities that a network adapter supports. The following flags are defined:




### -field MaxNumTrafficClasses

A <b>ULONG</b> value that specifies the maximum number of NDIS QoS traffic classes that the network adapter supports. For more information, see <a href="https://msdn.microsoft.com/0DE61F97-7173-4D91-90F3-20EAFB810251">NDIS QoS Traffic Classes</a>.
<div class="alert"><b>Note</b>  In order for the network adapter to support NDIS QoS for DCB, it must support at least three traffic classes.</div><div> </div>

### -field MaxNumEtsCapableTrafficClasses

A <b>ULONG</b> value that specifies the maximum number of QoS traffic classes that the network adapter can use with the  Enhanced Transmission Selection (ETS) algorithm. This value must be less than or equal to the value of the <b>MaxNumTrafficClasses</b> member.

 For more information about ETS, see <a href="https://msdn.microsoft.com/952ECB1E-96AD-4717-8E49-68558E7E9AD4">Enhanced Transmission Selection (ETS) Algorithm</a>.
<div class="alert"><b>Note</b>  In order for the network adapter to support NDIS QoS for DCB, it must support at least two ETS-capable traffic classes.</div><div> </div>

### -field MaxNumPfcEnabledTrafficClasses

A <b>ULONG</b> value that specifies the maximum number of QoS traffic classes that the network adapter can use with the   Priority-based Flow Control (PFC) algorithm. This value must be less than or equal to the value of the <b>MaxNumTrafficClasses</b> member.

For more information about PFC, see <a href="https://msdn.microsoft.com/9DD8A66F-273F-4E5A-99EF-33C2EDF3240C">Priority-based Flow Control (PFC)</a>.
<div class="alert"><b>Note</b>  In order for the network adapter to support NDIS QoS for DCB, it must support at least one PFC-capable traffic class.</div><div> </div>

##### - Flags.NDIS_QOS_CAPABILITIES_CEE_DCBX_SUPPORTED

If this flag is set, the network adapter and miniport driver supports the protocols that pre-date the IEEE 802.1Qaz Data Center Bridging Exchange (DCBX) protocol. These protocols include the Converged Enhanced Ethernet (CEE) suite of protocols.


##### - Header.NDIS_QOS_CAPABILITIES_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_QOS_CAPABILITIES_REVISION_1.


##### - Flags.NDIS_QOS_CAPABILITIES_MACSEC_BYPASS_SUPPORTED

If this flag is set, the network adapter supports the ability to bypass media access control security (MACsec) processing. For more information about MACsec, refer to the 802.1AE-2006 standard.


##### - Flags.NDIS_QOS_CAPABILITIES_STRICT_TSA_SUPPORTED

If this flag is set, the network adapter supports the strict priority transmission selection algorithm (TSA). For more information about this algorithm, see <a href="https://msdn.microsoft.com/7C7A34CA-673C-4EFC-970D-08458AA83EAD">Strict Priority Algorithm</a>.
<div class="alert"><b>Note</b>  In order to be compliant with DCB, the network adapter must support the strict priority TSA.</div><div> </div>

##### - Flags.NDIS_QOS_CAPABILITIES_IEEE_DCBX_SUPPORTED

If this flag is set, the network adapter and miniport driver supports the IEEE 802.1Qaz DCBX protocol.  The DCBX protocol allows DCB parameters to be exchanged between two directly connected peers. This allows these peers to adapt and tune these parameters in order to optimize data transfer over the connection. 
For more information about this protocol, see <a href="https://msdn.microsoft.com/FEB3FDBB-8A3C-4907-A6D0-CB5E94BCFEFF">Overview of Data Center Bridging</a>.
<div class="alert"><b>Note</b>  If this flag is set, the miniport driver must reject any send requests for DCBX packets.</div><div> </div>

## -remarks


The miniport driver registers the NDIS QoS capabilities of the underlying network adapter  from the driver's 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function by following these steps: 
<ol>
<li>
The miniport driver initializes an <b>NDIS_QOS_CAPABILITIES</b> structure with the NDIS QoS capabilities of the network adapter. 

</li>
<li>
The miniport driver initializes an  <a href="..\ndis\ns-ndis-_ndis_miniport_adapter_hardware_assist_attributes.md">NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a>
    structure with the other hardware-assisted  capabilities of the network adapter. The driver sets the <b>HardwareQosCapabilities</b> member of the <b>NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</b> structure to a pointer to the <b>NDIS_QOS_CAPABILITIES</b> structure. 

</li>
<li>
The miniport driver  calls <mshelp:link keywords="netvista.ndismsetminiportattributes" tabindex="0"><b>
    NdisMSetMiniportAttributes</b></mshelp:link> and sets the <i>MiniportAttributes</i> parameter to 
    a pointer to the <a href="..\ndis\ns-ndis-_ndis_miniport_adapter_hardware_assist_attributes.md">NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a>
    structure.

</li>
</ol>The <b>NDIS_QOS_CAPABILITIES</b> structure is also returned in OID query requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451827">OID_QOS_CURRENT_CAPABILITIES</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/hh451828">OID_QOS_HARDWARE_CAPABILITIES</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451827">OID_QOS_CURRENT_CAPABILITIES</a>

<mshelp:link keywords="netvista.ndismsetminiportattributes" tabindex="0"><b>
    NdisMSetMiniportAttributes</b></mshelp:link>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451828">OID_QOS_HARDWARE_CAPABILITIES</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_hardware_assist_attributes.md">NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a>

<b></b>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_QOS_CAPABILITIES structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

