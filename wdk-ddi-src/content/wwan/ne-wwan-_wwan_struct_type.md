---
UID: NE:wwan._WWAN_STRUCT_TYPE
title: "_WWAN_STRUCT_TYPE"
author: windows-driver-content
description: The WWAN_STRUCT_TYPE enumeration lists the different types of the list elements that follow the WWAN_LIST_HEADER object in memory.
old-location: netvista\wwan_struct_type.htm
old-project: netvista
ms.assetid: 43729964-9338-45ab-ad59-406176c1ae9f
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PWWAN_STRUCT_TYPE, PWWAN_STRUCT_TYPE, PWWAN_STRUCT_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_STRUCT_TYPE, WWAN_STRUCT_TYPE enumeration [Network Drivers Starting with Windows Vista], WwanRef_6b201902-91a4-45ee-bc26-2fd321ff7d8c.xml, WwanStructContext, WwanStructDeviceCellularClass, WwanStructDeviceServiceCommandId, WwanStructDeviceServiceEntry, WwanStructDeviceServiceGuid, WwanStructMax, WwanStructProvider, WwanStructProvider2, WwanStructReserved0, WwanStructReserved1, WwanStructReserved2, WwanStructReserved3, WwanStructSmsCdma, WwanStructSmsPdu, WwanStructTN, _WWAN_STRUCT_TYPE, netvista.wwan_struct_type, wwan/PWWAN_STRUCT_TYPE, wwan/WWAN_STRUCT_TYPE, wwan/WwanStructContext, wwan/WwanStructDeviceCellularClass, wwan/WwanStructDeviceServiceCommandId, wwan/WwanStructDeviceServiceEntry, wwan/WwanStructDeviceServiceGuid, wwan/WwanStructMax, wwan/WwanStructProvider, wwan/WwanStructProvider2, wwan/WwanStructReserved0, wwan/WwanStructReserved1, wwan/WwanStructReserved2, wwan/WwanStructReserved3, wwan/WwanStructSmsCdma, wwan/WwanStructSmsPdu, wwan/WwanStructTN"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wwan.h
api_name:
-	WWAN_STRUCT_TYPE
product: Windows
targetos: Windows
req.typenames: WWAN_STRUCT_TYPE, *PWWAN_STRUCT_TYPE
---

# _WWAN_STRUCT_TYPE enumeration


## -description


The WWAN_STRUCT_TYPE enumeration lists the different types of the list elements that follow the
  WWAN_LIST_HEADER object in memory.


## -enum-fields




### -field WwanStructTN

The elements are NULL-terminated strings of Telephone Number (TNs), with each string having
     WWAN_TN_LEN characters.
     


<a href="https://msdn.microsoft.com/library/windows/hardware/ff569833">OID_WWAN_READY_INFO</a> uses this value to
     represent a list of TNs assigned to the device.


### -field WwanStructContext

The elements are of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571201">WWAN_CONTEXT</a>.
     


<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-wwan-provisioned-contexts">
     OID_WWAN_PROVISIONED_CONTEXTS</a> uses this value to represent a list of provisioned
     contexts.


### -field WwanStructProvider

The elements are of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571223">WWAN_PROVIDER</a>.
     

Both <a href="https://msdn.microsoft.com/library/windows/hardware/ff569830">OID_WWAN_PREFERRED_PROVIDERS</a> and 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569843">OID_WWAN_VISIBLE_PROVIDERS</a> use this
     value to represent a list of network providers for WWAN 1.0 miniport drivers.


### -field WwanStructSmsPdu

The elements are of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571248">WWAN_SMS_PDU_RECORD</a>.


### -field WwanStructReserved0

The value is reserved for future use. Do not use.


### -field WwanStructReserved1

The value is reserved for future use. Do not use.


### -field WwanStructReserved2

The value is reserved for future use. Do not use.


### -field WwanStructSmsCdma

The elements are of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571243">WWAN_SMS_CDMA_RECORD</a>.


### -field WwanStructReserved3

The value is reserved for future use. Do not use.


### -field WwanStructDeviceServiceEntry

The elements are of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/hh831870">WWAN_DEVICE_SERVICE_ENTRY</a>.


### -field WwanStructProvider2

The elements are of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/hh464135">WWAN_PROVIDER2</a>.

The following OIDs use this value to represent a list of network providers for WWAN 2.0 miniport drivers:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff569830">OID_WWAN_PREFERRED_PROVIDERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569843">OID_WWAN_VISIBLE_PROVIDERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh831868">OID_WWAN_PREFERRED_MULTICARRIER_PROVIDERS</a>



### -field WwanStructDeviceServiceGuid

The elements are of type 
     GUID.


### -field WwanStructDeviceServiceCommandId

The elements are of type ULONG.


### -field WwanStructCellularClass


### -field WwanStructDeviceSlotMap


### -field WwanStructUiccApplication


### -field WwanStructRegisterAcquisitionOrder


### -field WwanStructRegistrationState


### -field WwanStructSignalState


### -field WwanStructUiccTerminalCapability


### -field WwanStructSarConfig


### -field WwanStructContextV2


### -field WwanStructNetworkBlacklistProvider


### -field WwanStructMax

The total number of supported types.


#### - WwanStructDeviceCellularClass

The elements are of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff571199">WWAN_CELLULAR_CLASS</a>. 


<a href="https://msdn.microsoft.com/library/windows/hardware/ff569824">OID_WWAN_DEVICE_CAPS</a> uses this value to represent multiple cellular classes supported by the miniport driver.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff569830">OID_WWAN_PREFERRED_PROVIDERS</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-wwan-provisioned-contexts">OID_WWAN_PROVISIONED_CONTEXTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569833">OID_WWAN_READY_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569843">OID_WWAN_VISIBLE_PROVIDERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571201">WWAN_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571208">WWAN_LIST_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571223">WWAN_PROVIDER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571243">WWAN_SMS_CDMA_RECORD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571248">WWAN_SMS_PDU_RECORD</a>
 

 

