---
UID: NS:bthddi._BTH_PROFILE_DRIVER_INTERFACE
title: "_BTH_PROFILE_DRIVER_INTERFACE"
author: windows-driver-content
description: The BTH_PROFILE_DRIVER_INTERFACE structure provides functions to allocate, free, initialize, and reuse BRBs, and to determine the currently installed Bluetooth version.
old-location: bltooth\bth_profile_driver_interface.htm
old-project: bltooth
ms.assetid: d4aa5fa9-966c-49c5-b41c-ca963a201e21
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: BTH_PROFILE_DRIVER_INTERFACE structure [Bluetooth Devices], bth_structs_0df6b87d-3846-49ed-9614-e83f2e828e7d.xml, bltooth.bth_profile_driver_interface, bthddi/BTH_PROFILE_DRIVER_INTERFACE, PBTH_PROFILE_DRIVER_INTERFACE, _BTH_PROFILE_DRIVER_INTERFACE, bthddi/PBTH_PROFILE_DRIVER_INTERFACE, PBTH_PROFILE_DRIVER_INTERFACE structure pointer [Bluetooth Devices], *PBTH_PROFILE_DRIVER_INTERFACE, BTH_PROFILE_DRIVER_INTERFACE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	bthddi.h
apiname:
-	BTH_PROFILE_DRIVER_INTERFACE
product: Windows
targetos: Windows
req.typenames: BTH_PROFILE_DRIVER_INTERFACE, *PBTH_PROFILE_DRIVER_INTERFACE
---

# _BTH_PROFILE_DRIVER_INTERFACE structure


## -description


The BTH_PROFILE_DRIVER_INTERFACE structure provides functions to allocate, free, initialize, and
  reuse BRBs, and to determine the currently installed Bluetooth version.


## -syntax


````
typedef struct _BTH_PROFILE_DRIVER_INTERFACE {
  INTERFACE                             Interface;
  PFNBTH_ALLOCATE_BRB                   BthAllocateBrb;
  PFNBTH_FREE_BRB                       BthFreeBrb;
  PFNBTH_INITIALIZE_BRB                 BthInitializeBrb;
  PFNBTH_REUSE_BRB                      BthReuseBrb;
  PFNBTH_IS_BLUETOOTH_VERSION_AVAILABLE IsBluetoothVersionAvailable;
} BTH_PROFILE_DRIVER_INTERFACE, *PBTH_PROFILE_DRIVER_INTERFACE;
````


## -struct-fields




### -field Interface

A structure that describes the 
     <b>BTH_PROFILE_DRIVER_INTERFACE</b> interface for use by profile drivers. For more information about this
     structure, see 
     <a href="..\miniport\ns-miniport-_interface.md">INTERFACE</a>.


### -field BthAllocateBrb

Pointer to the 
     <a href="..\bthddi\nc-bthddi-pfnbth_allocate_brb.md">BthAllocateBrb</a> function.


### -field BthFreeBrb

Pointer to the 
     <a href="..\bthddi\nc-bthddi-pfnbth_free_brb.md">BthFreeBrb</a> function.


### -field BthInitializeBrb

Pointer to the 
     <a href="..\bthddi\nc-bthddi-pfnbth_initialize_brb.md">BthInitializeBrb</a> function.


### -field BthReuseBrb

Pointer to the 
     <a href="..\bthddi\nc-bthddi-pfnbth_reuse_brb.md">BthReuseBrb</a> function.


### -field IsBluetoothVersionAvailable

Pointer to the 
     <a href="..\bthddi\nc-bthddi-pfnbth_is_bluetooth_version_available.md">
     IsBluetoothVersionAvailable</a> function.


## -remarks



Profile drivers should specify the 
    <b>GUID_BTHDDI_PROFILE_DRIVER_INTERFACE</b> GUID to query for an instance of the
    BTH_PROFILE_DRIVER_INTERFACE structure from the Bluetooth driver stack.

All the members of this structure, other than the 
    <b>Interface</b> member, are function pointers.




## -see-also

<a href="..\bthddi\nc-bthddi-pfnbth_allocate_brb.md">BthAllocateBrb</a>



<a href="..\bthddi\nc-bthddi-pfnbth_free_brb.md">BthFreeBrb</a>



<a href="..\bthddi\nc-bthddi-pfnbth_is_bluetooth_version_available.md">IsBluetoothVersionAvailable</a>



<a href="..\miniport\ns-miniport-_interface.md">INTERFACE</a>



<a href="..\bthddi\nc-bthddi-pfnbth_reuse_brb.md">BthReuseBrb</a>



<a href="..\bthddi\nc-bthddi-pfnbth_reuse_brb.md">BthReuseBrb</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20BTH_PROFILE_DRIVER_INTERFACE structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

