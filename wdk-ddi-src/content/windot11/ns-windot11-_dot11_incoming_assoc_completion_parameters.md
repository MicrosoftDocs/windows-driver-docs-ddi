---
UID: NS:windot11._DOT11_INCOMING_ASSOC_COMPLETION_PARAMETERS
title: _DOT11_INCOMING_ASSOC_COMPLETION_PARAMETERS (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_incoming_assoc_completion_parameters.htm
tech.root: netvista
ms.assetid: 8f3cfe07-5026-40fb-b832-da5ae048843e
ms.date: 02/16/2018
ms.keywords: "*PDOT11_INCOMING_ASSOC_COMPLETION_PARAMETERS, DOT11_INCOMING_ASSOC_COMPLETION_PARAMETERS, DOT11_INCOMING_ASSOC_COMPLETION_PARAMETERS structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_fac44c06-59c5-4fd3-a8ec-335d9e9c6f7d.xml, PDOT11_INCOMING_ASSOC_COMPLETION_PARAMETERS, PDOT11_INCOMING_ASSOC_COMPLETION_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _DOT11_INCOMING_ASSOC_COMPLETION_PARAMETERS, netvista.dot11_incoming_assoc_completion_parameters, windot11/DOT11_INCOMING_ASSOC_COMPLETION_PARAMETERS, windot11/PDOT11_INCOMING_ASSOC_COMPLETION_PARAMETERS"
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   system.
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
-	DOT11_INCOMING_ASSOC_COMPLETION_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: DOT11_INCOMING_ASSOC_COMPLETION_PARAMETERS, *PDOT11_INCOMING_ASSOC_COMPLETION_PARAMETERS
product:
- Windows 10 or later.
---

# _DOT11_INCOMING_ASSOC_COMPLETION_PARAMETERS structure


## -description

<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div>

The DOT11_INCOMING_ASSOC_COMPLETION_PARAMETERS structure specifies the results of the association operation that is performed by the 802.11 station after it receives an association request from a peer station on an infrastructure BSS.

## -syntax

```cpp
typedef struct _DOT11_INCOMING_ASSOC_COMPLETION_PARAMETERS {
  NDIS_OBJECT_HEADER     Header;
  DOT11_MAC_ADDRESS      PeerMacAddr;
  ULONG                  uStatus;
  UCHAR                  ucErrorSource;
  BOOLEAN                bReAssocReq;
  BOOLEAN                bReAssocResp;
  ULONG                  uAssocReqOffset;
  ULONG                  uAssocReqSize;
  ULONG                  uAssocRespOffset;
  ULONG                  uAssocRespSize;
  DOT11_AUTH_ALGORITHM   AuthAlgo;
  DOT11_CIPHER_ALGORITHM UnicastCipher;
  DOT11_CIPHER_ALGORITHM MulticastCipher;
  ULONG                  uActivePhyListOffset;
  ULONG                  uActivePhyListSize;
  ULONG                  uBeaconOffset;
  ULONG                  uBeaconSize;
} DOT11_INCOMING_ASSOC_COMPLETION_PARAMETERS, *PDOT11_INCOMING_ASSOC_COMPLETION_PARAMETERS;
```


## -struct-fields




### -field Header

The type, revision, and size of the DOT11_INCOMING_ASSOC_COMPLETION_PARAMETERS structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the members of <b>Header</b> to the following values:

#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.

#### Revision

This member must be set to DOT11_INCOMING_ASSOC_COMPLETION_PARAMETERS_REVISION_1.

#### Size

This member must be set to <b>sizeof</b>(DOT11_INCOMING_ASSOC_COMPLETION_PARAMETERS).

For more information about these members, see <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field PeerMacAddr

The media access control (MAC) address of the peer station that sent an association request.

### -field uStatus

The status of the association with the peer station. If zero, the association succeeds. If nonzero, the association fails.

### -field ucErrorSource

For nonzero values of <b>uStatus</b>, this member indicates the source of the error that prevents association. The NIC must set <b>ucErrorSource</b> to one of the following values:

#### DOT11_ASSOC_ERROR_SOURCE_OS

The miniport driver has rejected the association procedure because of system errors, such as out-of-memory errors. In this case, <b>uStatus</b> should be set to the NDIS_STATUS_XXX or NTSTATUS_XXX code returned from the operating system.


#### DOT11_ASSOC_ERROR_SOURCE_REMOTE

The AP or the peer station has rejected the association procedure. In this case, <b>uStatus</b> should be set to the 802.11 status code form the 802.11 authentication frame, association response frame, or re-association response frame. Table 19 in the <i>IEEE 802.11-2003 Specification</i> contains all the possible values. The miniport driver can also return new values in this IEEE specification when it is amended.

#### DOT11_ASSOC_ERROR_SOURCE_OTHER

The association failed for an IHV-specific reason. In this case, <b>uStatus</b> contains a nonzero value specified by the IHV.

### -field bReAssocReq

A Boolean value that indicates whether the request from the peer station is a re-association request.


### -field bReAssocResp

A Boolean value that indicates whether the response from the NIC is a re-association request.


### -field uAssocReqOffset

The offset of the request frame that is used in the association operation. The frame includes information elements (IEs) but does not include the 802.11 MAC header.


### -field uAssocReqSize

The length, in bytes, of the request frame that is used in the association operation. The frame includes information elements (IEs) but does not include the 802.11 MAC header.


### -field uAssocRespOffset

The offset of the response frame that is used in the association operation. The frame includes information elements (IEs) but does not include the 802.11 MAC header.


### -field uAssocRespSize

The length of the response frame, in bytes, that is used in the association operation. The frame includes information elements (IEs) but does not include the 802.11 MAC header.


### -field AuthAlgo

The authentication algorithm that the 802.11 station resolved with the peer station during the association operation. For more information about the data type for the <b>AuthAlgo</b> member, see <a href="..\wlantypes\ne-wlantypes-_dot11_auth_algorithm.md">DOT11_AUTH_ALGORITHM</a>.

<div class="alert"><b>Note</b>  The miniport driver must set this member to zero if <b>uStatus</b> is not set to zero.</div>

### -field UnicastCipher

The unicast cipher algorithm that the 802.11 station resolved with the peer station during the association operation. For more information about the data type for the
      <b>UnicastCipher</b> member, see <a href="..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md">DOT11_CIPHER_ALGORITHM</a>.

<div class="alert"><b>Note</b>  The miniport driver must set this member to zero if <b>uStatus</b> is not set to zero.</div>

### -field MulticastCipher

The multicast cipher algorithm that the 802.11 station resolved with the AP or peer station during the association operation. For more information about the data type for the <b>MulticastCipher</b> member, see <a href="..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md">DOT11_CIPHER_ALGORITHM</a>.

<div class="alert"><b>Note</b>  The miniport driver must set this member to zero if <b>uStatus</b> is not set to zero.</div>

### -field uActivePhyListOffset

The offset of the list of PHY identifiers (IDs) that the 802.11 station uses to send or receive packets on the BSS network connection. Each entry is a ULONG value.

The Extensible Station (ExtSTA) <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-active-phy-list">msDot11ActivePhyList</a> MIB objec also references the active PHY list.

Entries in the active PHY list can be one of the following values:

<ul>
<li>
A PHY ID that is specified by the Extensible Station (ExtSTA)
        <b>msDot11DesiredPhyList</b> management information base (MIB) object. For more information about this
        MIB object, see
        <a href="https://msdn.microsoft.com/library/windows/hardware/ff569144">OID_DOT11_DESIRED_PHY_LIST</a>.

</li>
<li>
A PHY ID of DOT11_PHY_ID_ANY. The miniport driver can set an entry to this value if the ExtSTA
        <b>msDot11ActivePhyList</b> MIB object specifies all of the PHY IDs that are specified by the
        <b>msDot11DesiredPhyList</b> MIB object. For more information about this MIB object, see
        <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-active-phy-list">OID_DOT11_ACTIVE_PHY_LIST</a>.

<div class="alert"><b>Note</b>  An entry with the value of DOT11_PHY_ID_ANY must be the only entry in the
        active PHY list.</div>
</li>
</ul>
The offset of the active PHY list is relative to the start of the buffer that contains the
      DOT11_ASSOCIATION_COMPLETION_PARAMETERS structure.

<div class="alert"><b>Note</b>  The miniport driver must set this member to zero if
      <b>uStatus</b> is not set to zero.</div>

### -field uActivePhyListSize

The length, in bytes, of the active PHY list. The
     <b>uActivePhyListSize</b> member must be a multiple of
     <code>sizeof(ULONG)</code>.


<div class="alert"><b>Note</b>  The miniport driver must set this member to zero if
     <b>uStatus</b> is not set to zero.</div>

### -field uBeaconOffset

The offset, in bytes, of the last transmitted 802.11 Beacon frame.


The Beacon frame includes the Beacon frame header and all information elements (IEs), but it does not
     include the 802.11 MAC header. The Beacon frame format is defined in ISO/IEC 8802-11.

The Beacon frame should be the latest frame used by the driver, except that real-time parameters or
     IEs that vary with data frame flow control, or client association status such as timestamp, radio
     parameters, TIM, ERP, and HT IEs, do not need to be accurate,

<div class="alert"><b>Note</b>  The miniport driver must set this member to zero if
     <b>uStatus</b> is not set to zero.</div>

### -field uBeaconSize

The length, in bytes, of the last transmitted 802.11 Beacon frame.


The Beacon frame includes the Beacon frame header and all information elements (IEs), but it does not
     include the 802.11 MAC header. The Beacon frame format is defined in ISO/IEC 8802-11.

The Beacon frame should be the latest frame used by the driver, except that real-time parameters or
     IEs that vary with data frame flow control, or client association status such as timestamp, radio
     parameters, TIM, ERP, and HT IEs, do not need to be accurate,

<div class="alert"><b>Note</b>  The miniport driver must set this member to zero if
     <b>uStatus</b> is not set to zero.</div>


## -remarks



The Native 802.11 miniport driver includes a DOT11_INCOMING_ASSOC_COMPLETION_PARAMETERS structure when
    the driver makes an
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff547647">
    NDIS_STATUS_DOT11_INCOMING_ASSOC_COMPLETION</a> status indication.

The NDIS_STATUS_DOT11_INCOMING_ASSOC_COMPLETION status indication marks the end of an
    <i>association indication block</i>. If the association is successful, the NIC must make the
    NDIS_STATUS_DOT11_INCOMING_ASSOC_COMPLETION indication after it successfully sends the corresponding
    association response frame to the station that originally requested the association. If the association
    fails, the NIC must make the NDIS_STATUS_DOT11_INCOMING_ASSOC_COMPLETION indication whether the response
    is sent successfully or not. The failure can be because the NIC or operating system reject the
    association request or because of a failure not related to the 802.11 framework.




## -see-also

<a href="..\wlantypes\ne-wlantypes-_dot11_auth_algorithm.md">DOT11_AUTH_ALGORITHM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547647">
   NDIS_STATUS_DOT11_INCOMING_ASSOC_COMPLETION</a>



<a href="..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md">DOT11_CIPHER_ALGORITHM</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 


