---
UID: NS:windot11._DOT11_WFD_DISCOVER_REQUEST
title: _DOT11_WFD_DISCOVER_REQUEST
author: windows-driver-content
description: The OID_DOT11_WFD_DISCOVER_REQUEST structure is the input data for an OID_DOT11_WFD_DISCOVER_REQUEST request. The structure contains the parameters for a Wi-Fi Direct device discovery.
old-location: netvista\_dot11_wfd_discover_request.htm
old-project: netvista
ms.assetid: 231318AA-9112-41E2-9E7A-FEC64E5FB30A
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista._dot11_wfd_discover_request, PDOT11_WFD_DISCOVER_REQUEST structure pointer [Network Drivers Starting with Windows Vista], windot11/PDOT11_WFD_DISCOVER_REQUEST, DOT11_WFD_DISCOVER_REQUEST, PDOT11_WFD_DISCOVER_REQUEST, DOT11_WFD_DISCOVER_REQUEST structure [Network Drivers Starting with Windows Vista], *PDOT11_WFD_DISCOVER_REQUEST, _DOT11_WFD_DISCOVER_REQUEST, windot11/ DOT11_WFD_DISCOVER_REQUEST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows 8
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Windot11.h
apiname: 
-	DOT11_WFD_DISCOVER_REQUEST
product: Windows
targetos: Windows
req.typenames: *PDOT11_WFD_DISCOVER_REQUEST, DOT11_WFD_DISCOVER_REQUEST
req.product: Windows 10 or later.
---

# _DOT11_WFD_DISCOVER_REQUEST structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The <b>OID_DOT11_WFD_DISCOVER_REQUEST</b> structure is the input  data for an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451795">OID_DOT11_WFD_DISCOVER_REQUEST</a> request.  The structure contains the parameters for a Wi-Fi Direct device discovery.


## -syntax


````
typedef struct _DOT11_WFD_DISCOVER_REQUEST {
  NDIS_OBJECT_HEADER      Header;
  DOT11_WFD_DISCOVER_TYPE DiscoverType;
  DOT11_WFD_SCAN_TYPE     ScanType;
  ULONG                   uDiscoverTimeout;
  ULONG                   uDeviceFilterListOffset;
  ULONG                   uNumDeviceFilters;
  ULONG                   uIEsOffset;
  ULONG                   uIEsLength;
  BOOLEAN                 bForceScanLegacyNetworks;
} DOT11_WFD_DISCOVER_REQUEST, *PDOT11_WFD_DISCOVER_REQUEST;
````


## -struct-fields




### -field Header

The type, revision, and size of the<b>OID_DOT11_WFD_DISCOVER_REQUEST</b> structure. This member is formatted as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <b>Header</b> to the following values:



For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field DiscoverType

The device discovery mode to use.


### -field ScanType

Scanning type used during the scan phase of device discovery.


### -field uDiscoverTimeout

Maximum time, in milliseconds, to complete the discovery operation. A miniport can complete a discovery in less time, however, it should not use any more time than specified by this value. This is the total time allowed for completion of all phases of device discovery.


### -field uDeviceFilterListOffset

The offset to the list of P2P Device filters, which specifies the P2P devices and Group Owners to search for during Wi-Fi Direct device discovery. This offset is specified in bytes and is relative to the start of the buffer that contains the DOT11_WFD_DISCOVER_REQUEST structure. Each entry in the list is formatted as a DOT11_WFD_DISCOVER_DEVICE_FILTER.

When a list entry specifies a non-broadcast MAC address as the Device ID, the driver must use this MAC address in the Device ID Attribute of the P2P IEs it includes in the probe requests.

The offset in the <b>InformationBuffer</b> of the <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> where a list of P2P device identifiers begins. These are the identifiers to for during device discovery.


### -field uNumDeviceFilters

The number of P2P device filters to use during WFD device discovery. The default value for this field is 0.


### -field uIEsOffset

The offset in the <b>InformationBuffer</b> of the <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure where the additional Informational Elements (IEs) begin.


### -field uIEsLength

The length, in bytes, of the additional IEs which the Wi-Fi Direct device port must add to the probe request packet. If this value is 0, the system did not provide any IEs and the miniport must insert the  default IEs in the probe request packet. The default IEs are in  <b>DefaultRequestIEs</b> received earlier with an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451790">OID_DOT11_WFD_ADDITIONAL_IE</a> request.


### -field bForceScanLegacyNetworks

When TRUE, the Wi-Fi Direct device must also attempt to discover legacy networks. Otherwise, scanning for legacy networks is not necessary.


##### - Header.Revision

This member must be set to <b>DOT11_WFD_DISCOVER_REQUEST_REVISION_1</b>.


##### - Header.Type

This member must be set to <b>NDIS_OBJECT_TYPE_DEFAULT</b>.


##### - Header.Size

This member must be set to 
       <b>sizeof</b>(<b>DOT11_SIZEOF_WFD_DISCOVER_REQUEST_REVISION_1</b>).


## -remarks


Each entry in the device identifier list at <b>uDeviceFilterListOffset</b> is formatted as a <a href="..\windot11\ns-windot11-_dot11_mac_address.md">DOT11_MAC_ADDRESS</a> structure. When a non-broadcast MAC address is specified in this list, the driver must use this address in the Device ID attribute of the P2P IEs probe requests it transmits

The IEs present at <b>uIEsOffset</b>, for the duration of the device discovery, will temporarily replace IEs found at <b>DefaultRequestIEs</b> in input structure of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451790">OID_DOT11_WFD_ADDITIONAL_IE</a> request.



## -see-also

<a href="..\windot11\ne-windot11-_dot11_wfd_scan_type.md">DOT11_WFD_SCAN_TYPE</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<a href="..\windot11\ne-windot11-_dot11_wfd_discover_type.md">DOT11_WFD_DISCOVER_TYPE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451795">OID_DOT11_WFD_DISCOVER_REQUEST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20 DOT11_WFD_DISCOVER_REQUEST structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

