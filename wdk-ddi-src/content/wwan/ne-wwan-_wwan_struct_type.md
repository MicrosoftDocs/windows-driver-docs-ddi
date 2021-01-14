---
UID: NE:wwan._WWAN_STRUCT_TYPE
title: _WWAN_STRUCT_TYPE (wwan.h)
description: The WWAN_STRUCT_TYPE enumeration lists the different types of the list elements that follow the WWAN_LIST_HEADER object in memory.
old-location: netvista\wwan_struct_type.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WWAN_STRUCT_TYPE enumeration"]
ms.keywords: "*PWWAN_STRUCT_TYPE, PWWAN_STRUCT_TYPE, PWWAN_STRUCT_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_STRUCT_TYPE, WWAN_STRUCT_TYPE enumeration [Network Drivers Starting with Windows Vista], WwanRef_6b201902-91a4-45ee-bc26-2fd321ff7d8c.xml, WwanStructContext, WwanStructDeviceCellularClass, WwanStructDeviceServiceCommandId, WwanStructDeviceServiceEntry, WwanStructDeviceServiceGuid, WwanStructMax, WwanStructProvider, WwanStructProvider2, WwanStructReserved0, WwanStructReserved1, WwanStructReserved2, WwanStructReserved3, WwanStructSmsCdma, WwanStructSmsPdu, WwanStructTN, _WWAN_STRUCT_TYPE, netvista.wwan_struct_type, wwan/PWWAN_STRUCT_TYPE, wwan/WWAN_STRUCT_TYPE, wwan/WwanStructContext, wwan/WwanStructDeviceCellularClass, wwan/WwanStructDeviceServiceCommandId, wwan/WwanStructDeviceServiceEntry, wwan/WwanStructDeviceServiceGuid, wwan/WwanStructMax, wwan/WwanStructProvider, wwan/WwanStructProvider2, wwan/WwanStructReserved0, wwan/WwanStructReserved1, wwan/WwanStructReserved2, wwan/WwanStructReserved3, wwan/WwanStructSmsCdma, wwan/WwanStructSmsPdu, wwan/WwanStructTN"
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
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
targetos: Windows
req.typenames: WWAN_STRUCT_TYPE, *PWWAN_STRUCT_TYPE
f1_keywords:
 - _WWAN_STRUCT_TYPE
 - wwan/_WWAN_STRUCT_TYPE
 - PWWAN_STRUCT_TYPE
 - wwan/PWWAN_STRUCT_TYPE
 - WWAN_STRUCT_TYPE
 - wwan/WWAN_STRUCT_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_STRUCT_TYPE
 - PWWAN_STRUCT_TYPE
 - WWAN_STRUCT_TYPE
---

# _WWAN_STRUCT_TYPE enumeration


## -description

> [!IMPORTANT]
> ### Bias-free communication
>
> Microsoft supports a diverse and inclusive environment. This article contains references to terminology that the Microsoft [style guide for bias-free communication](/style-guide/bias-free-communication) recognizes as exclusionary. The word or phrase is used in this article for consistency because it currently appears in the software. When the software is updated to remove the language, this article will be updated to be in alignment.

The WWAN_STRUCT_TYPE enumeration lists the different types of the list elements that follow the
  WWAN_LIST_HEADER object in memory.

## -enum-fields

### -field WwanStructTN

The elements are NULL-terminated strings of Telephone Number (TNs), with each string having
     WWAN_TN_LEN characters.
     


<a href="/windows-hardware/drivers/network/oid-wwan-ready-info">OID_WWAN_READY_INFO</a> uses this value to
     represent a list of TNs assigned to the device.

### -field WwanStructContext

The elements are of type 
     <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_context">WWAN_CONTEXT</a>.
     


<a href="/windows-hardware/drivers/network/oid-wwan-provisioned-contexts">
     OID_WWAN_PROVISIONED_CONTEXTS</a> uses this value to represent a list of provisioned
     contexts.

### -field WwanStructProvider

The elements are of type 
     <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_provider">WWAN_PROVIDER</a>.
     

Both <a href="/windows-hardware/drivers/network/oid-wwan-preferred-providers">OID_WWAN_PREFERRED_PROVIDERS</a> and 
     <a href="/windows-hardware/drivers/network/oid-wwan-visible-providers">OID_WWAN_VISIBLE_PROVIDERS</a> use this
     value to represent a list of network providers for WWAN 1.0 miniport drivers.

### -field WwanStructSmsPdu

The elements are of type 
     <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_sms_pdu_record">WWAN_SMS_PDU_RECORD</a>.

### -field WwanStructReserved0

The value is reserved for future use. Do not use.

### -field WwanStructReserved1

The value is reserved for future use. Do not use.

### -field WwanStructReserved2

The value is reserved for future use. Do not use.

### -field WwanStructSmsCdma

The elements are of type 
     <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_sms_cdma_record">WWAN_SMS_CDMA_RECORD</a>.

### -field WwanStructReserved3

The value is reserved for future use. Do not use.

### -field WwanStructDeviceServiceEntry

The elements are of type 
     <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_device_service_entry">WWAN_DEVICE_SERVICE_ENTRY</a>.

### -field WwanStructProvider2

The elements are of type 
     <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_provider2">WWAN_PROVIDER2</a>.

The following OIDs use this value to represent a list of network providers for WWAN 2.0 miniport drivers:


<a href="/windows-hardware/drivers/network/oid-wwan-preferred-providers">OID_WWAN_PREFERRED_PROVIDERS</a>



<a href="/windows-hardware/drivers/network/oid-wwan-visible-providers">OID_WWAN_VISIBLE_PROVIDERS</a>



<a href="/windows-hardware/drivers/network/oid-wwan-preferred-multicarrier-providers">OID_WWAN_PREFERRED_MULTICARRIER_PROVIDERS</a>

### -field WwanStructDeviceServiceGuid

The elements are of type 
     GUID.

### -field WwanStructDeviceServiceCommandId

The elements are of type ULONG.

### -field WwanStructCellularClass

The elements are of type [WWAN_CELLULAR_CLASS](ne-wwan-_wwan_cellular_class.md).

### -field WwanStructDeviceSlotMap

The elements are of type [WWAN_DEVICE_SLOT_MAPPING_INFO](ns-wwan-_wwan_device_slot_mapping_info.md).

### -field WwanStructUiccApplication

The elements are of type BYTE for a UICC application ID.

### -field WwanStructRegisterAcquisitionOrder

The elements are of type ULONG.

### -field WwanStructRegistrationState

The elements are of type [WWAN_REGISTRATION_STATE](ns-wwan-_wwan_registration_state.md).

### -field WwanStructSignalState

The elements are of type [WWAN_SIGNAL_STATE](ns-wwan-_wwan_signal_state.md).

### -field WwanStructUiccTerminalCapability

The elements are of type **WWAN_UICC_TERMINAL_CAPABILITY_TLV**. For more info about low level UICC operations, see [MB low level UICC access](/windows-hardware/drivers/network/mb-low-level-uicc-access#mbimcidmsuiccterminalcapability).

### -field WwanStructSarConfig

The elements are of type [**WWAN_SAR_CONFIG_INDICES**](ns-wwan-_wwan_sar_config_indices.md). For more info about MB SAR operations, see [MB SAR Platform Support](/windows-hardware/drivers/network/mb-sar-platform-support#mbimcidmssarconfig).

### -field WwanStructContextV2

The elements are of type [**WWAN_CONTEXT_V2**](ns-wwan-_wwan_context_v2.md).

### -field WwanStructNetworkBlacklistProvider

The elements are of type [**WWAN_NETWORK_BLACKLIST_PROVIDER**](ns-wwan-_wwan_network_blacklist_provider.md). For more info about network blacklist providers, see [MB Network Blacklist Operations](/windows-hardware/drivers/network/mb-network-blacklist-operations).

### -field WwanStructMax

The total number of supported types.


#### - WwanStructDeviceCellularClass

The elements are of type <a href="/windows-hardware/drivers/ddi/wwan/ne-wwan-_wwan_cellular_class">WWAN_CELLULAR_CLASS</a>. 


<a href="/windows-hardware/drivers/network/oid-wwan-device-caps">OID_WWAN_DEVICE_CAPS</a> uses this value to represent multiple cellular classes supported by the miniport driver.

## -see-also

<a href="/windows-hardware/drivers/network/oid-wwan-preferred-providers">OID_WWAN_PREFERRED_PROVIDERS</a>



<a href="/windows-hardware/drivers/network/oid-wwan-provisioned-contexts">OID_WWAN_PROVISIONED_CONTEXTS</a>



<a href="/windows-hardware/drivers/network/oid-wwan-ready-info">OID_WWAN_READY_INFO</a>



<a href="/windows-hardware/drivers/network/oid-wwan-visible-providers">OID_WWAN_VISIBLE_PROVIDERS</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_context">WWAN_CONTEXT</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_list_header">WWAN_LIST_HEADER</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_provider">WWAN_PROVIDER</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_sms_cdma_record">WWAN_SMS_CDMA_RECORD</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_sms_pdu_record">WWAN_SMS_PDU_RECORD</a>

