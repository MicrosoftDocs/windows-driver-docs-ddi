---
UID: NS:windot11._DOT11_INCOMING_ASSOC_DECISION
title: "_DOT11_INCOMING_ASSOC_DECISION" (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_incoming_assoc_decision.htm
tech.root: netvista
ms.assetid: aaddff8c-71da-475b-a395-ac40b3b787ae
ms.date: 02/16/2018
ms.keywords: "*PDOT11_INCOMING_ASSOC_DECISION, DOT11_INCOMING_ASSOC_DECISION, DOT11_INCOMING_ASSOC_DECISION structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_d6449324-f2b1-492f-849b-d4510b44e94f.xml, PDOT11_INCOMING_ASSOC_DECISION, PDOT11_INCOMING_ASSOC_DECISION structure pointer [Network Drivers Starting with Windows Vista], Revision, Size, Type, _DOT11_INCOMING_ASSOC_DECISION, netvista.dot11_incoming_assoc_decision, windot11/DOT11_INCOMING_ASSOC_DECISION, windot11/PDOT11_INCOMING_ASSOC_DECISION"
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   systems.
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
-	windot11.h
api_name:
-	DOT11_INCOMING_ASSOC_DECISION
product:
- Windows
targetos: Windows
req.typenames: DOT11_INCOMING_ASSOC_DECISION, *PDOT11_INCOMING_ASSOC_DECISION
product:
- Windows 10 or later.
---

# _DOT11_INCOMING_ASSOC_DECISION structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_INCOMING_ASSOC_DECISION structure specifies the miniport driver's decision whether to
  accept an incoming association request from a peer station on an infrastructure BSS.


## -syntax


```cpp
typedef struct _DOT11_INCOMING_ASSOC_DECISION {
  NDIS_OBJECT_HEADER Header;
  DOT11_MAC_ADDRESS  PeerMacAddr;
  BOOLEAN            bAccept;
  USHORT             usReasonCode;
  ULONG              uAssocResponseIEsOffset;
  ULONG              uAssocResponseIEsLength;
} DOT11_INCOMING_ASSOC_DECISION, *PDOT11_INCOMING_ASSOC_DECISION;
```


## -struct-fields




### -field Header

The type, revision, and size of the DOT11_INCOMING_ASSOC_DECISION structure. This member is
     formatted as an
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.


The miniport driver must set the members of
     <b>Header</b> to the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="Type"></a><a id="type"></a><a id="TYPE"></a><dl>
<dt><b>Type</b></dt>
</dl>
</td>
<td width="60%">
This member must be set to NDIS_OBJECT_TYPE_DEFAULT.

</td>
</tr>
<tr>
<td width="40%"><a id="Revision"></a><a id="revision"></a><a id="REVISION"></a><dl>
<dt><b>Revision</b></dt>
</dl>
</td>
<td width="60%">
This member must be set to DOT11_INCOMING_ASSOC_DECISION_REVISION_1.

</td>
</tr>
<tr>
<td width="40%"><a id="Size"></a><a id="size"></a><a id="SIZE"></a><dl>
<dt><b>Size</b></dt>
</dl>
</td>
<td width="60%">
This member must be set to
       <code>sizeof(DOT11_INCOMING_ASSOC_DECISION)</code>.

</td>
</tr>
</table>
 

For more information about these members, see
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field PeerMacAddr

The media access control (MAC) address of the peer station that the 802.11 station attempted to
     connect to.


### -field bAccept

A Boolean value that indicates whether the miniport driver accepts the incoming association
     request. If <b>TRUE</b>, the driver instructs the NIC to accept the association request. Otherwise, the NIC
     should reject the request.


### -field usReasonCode

A USHORT value that represents a reason code to include in the NIC's association response if
     <b>bAccept</b> is <b>FALSE</b>.


### -field uAssocResponseIEsOffset

The offset of the additional information elements (IEs), in bytes, which the NIC must add to the
     association response frame that it sends to the peer station that seeks association. This offset is relative
     to the start of the buffer that contains the DOT11_INCOMING_ASSOC_DECISION structure. The default value
     is zero.


### -field uAssocResponseIEsLength

The length of the additional information elements (IEs), in bytes, which the NIC must add to the
     probe response frame that it sends to the peer station that seeks association. The default value is
     zero.


## -remarks



This structure is used with
    <a href="https://msdn.microsoft.com/library/windows/hardware/hh406480">
    OID_DOT11_INCOMING_ASSOCIATION_DECISION</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406480">
   OID_DOT11_INCOMING_ASSOCIATION_DECISION</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 


