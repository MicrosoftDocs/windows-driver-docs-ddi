---
UID: NS:bthddi._BTH_PROFILE_DRIVER_INTERFACE
title: _BTH_PROFILE_DRIVER_INTERFACE (bthddi.h)
description: The BTH_PROFILE_DRIVER_INTERFACE structure provides functions to allocate, free, initialize, and reuse BRBs, and to determine the currently installed Bluetooth version.
old-location: bltooth\bth_profile_driver_interface.htm
tech.root: bltooth
ms.assetid: d4aa5fa9-966c-49c5-b41c-ca963a201e21
ms.date: 04/27/2018
keywords: ["_BTH_PROFILE_DRIVER_INTERFACE structure"]
ms.keywords: "*PBTH_PROFILE_DRIVER_INTERFACE, BTH_PROFILE_DRIVER_INTERFACE, BTH_PROFILE_DRIVER_INTERFACE structure [Bluetooth Devices], PBTH_PROFILE_DRIVER_INTERFACE, PBTH_PROFILE_DRIVER_INTERFACE structure pointer [Bluetooth Devices], _BTH_PROFILE_DRIVER_INTERFACE, bltooth.bth_profile_driver_interface, bth_structs_0df6b87d-3846-49ed-9614-e83f2e828e7d.xml, bthddi/BTH_PROFILE_DRIVER_INTERFACE, bthddi/PBTH_PROFILE_DRIVER_INTERFACE"
f1_keywords:
 - "bthddi/BTH_PROFILE_DRIVER_INTERFACE"
 - "BTH_PROFILE_DRIVER_INTERFACE"
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- bthddi.h
api_name:
- BTH_PROFILE_DRIVER_INTERFACE
product:
- Windows
targetos: Windows
req.typenames: BTH_PROFILE_DRIVER_INTERFACE, *PBTH_PROFILE_DRIVER_INTERFACE
---

# _BTH_PROFILE_DRIVER_INTERFACE structure


## -description


The BTH_PROFILE_DRIVER_INTERFACE structure provides functions to allocate, free, initialize, and
  reuse BRBs, and to determine the currently installed Bluetooth version.


## -struct-fields




### -field Interface

A structure that describes the 
     <b>BTH_PROFILE_DRIVER_INTERFACE</b> interface for use by profile drivers. For more information about this
     structure, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a>.


### -field BthAllocateBrb

Pointer to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/nc-bthddi-pfnbth_allocate_brb">BthAllocateBrb</a> function.


### -field BthFreeBrb

Pointer to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/nc-bthddi-pfnbth_free_brb">BthFreeBrb</a> function.


### -field BthInitializeBrb

Pointer to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/nc-bthddi-pfnbth_initialize_brb">BthInitializeBrb</a> function.


### -field BthReuseBrb

Pointer to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/nc-bthddi-pfnbth_reuse_brb">BthReuseBrb</a> function.


### -field IsBluetoothVersionAvailable

Pointer to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/nc-bthddi-pfnbth_is_bluetooth_version_available">
     IsBluetoothVersionAvailable</a> function.


## -remarks



Profile drivers should specify the 
    <b>GUID_BTHDDI_PROFILE_DRIVER_INTERFACE</b> GUID to query for an instance of the
    BTH_PROFILE_DRIVER_INTERFACE structure from the Bluetooth driver stack.

All the members of this structure, other than the 
    <b>Interface</b> member, are function pointers.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/nc-bthddi-pfnbth_allocate_brb">BthAllocateBrb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/nc-bthddi-pfnbth_free_brb">BthFreeBrb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/nc-bthddi-pfnbth_initialize_brb">BthInitializeBrb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/nc-bthddi-pfnbth_reuse_brb">BthReuseBrb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/nc-bthddi-pfnbth_is_bluetooth_version_available">IsBluetoothVersionAvailable</a>
 

 

