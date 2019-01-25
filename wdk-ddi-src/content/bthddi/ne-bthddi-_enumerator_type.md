---
UID: NE:bthddi._ENUMERATOR_TYPE
title: "_ENUMERATOR_TYPE" (bthddi.h)
description: The ENUMERATOR_TYPE enumeration type is used to determine whether the enumerated device is associated with a service or a protocol. The ENUMERATOR_TYPE enumeration is intended for internal use only and should not be used by profile drivers.
old-location: bltooth\enumerator_type.htm
tech.root: bltooth
ms.assetid: 2f8ae260-3a4c-44a5-85b7-e3ebcf21522b
ms.date: 04/27/2018
ms.keywords: "*PENUMERATOR_TYPE, ENUMERATOR_TYPE, ENUMERATOR_TYPE enumeration [Bluetooth Devices], ENUMERATOR_TYPE_MAX, ENUMERATOR_TYPE_PROTOCOL, ENUMERATOR_TYPE_SERVICE, PENUMERATOR_TYPE, PENUMERATOR_TYPE enumeration pointer [Bluetooth Devices], _ENUMERATOR_TYPE, bltooth.enumerator_type, bth_enums_48fc8cf9-53b6-46fd-831a-f4a5c56ff3f1.xml, bthddi/ENUMERATOR_TYPE, bthddi/ENUMERATOR_TYPE_MAX, bthddi/ENUMERATOR_TYPE_PROTOCOL, bthddi/ENUMERATOR_TYPE_SERVICE, bthddi/PENUMERATOR_TYPE"
ms.topic: enum
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthddi.h
api_name:
-	ENUMERATOR_TYPE
product:
- Windows
targetos: Windows
req.typenames: ENUMERATOR_TYPE, *PENUMERATOR_TYPE
---

# _ENUMERATOR_TYPE enumeration


## -description


The ENUMERATOR_TYPE enumeration type is used to determine whether the enumerated device is associated
  with a service or a protocol. The ENUMERATOR_TYPE enumeration is intended for internal use only and should
  not be used by profile drivers.


## -enum-fields




### -field ENUMERATOR_TYPE_PROTOCOL

For internal use only. Do not use.


### -field ENUMERATOR_TYPE_SERVICE

This value should be specified for profile drivers. For more information about how this value is
     used, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536643">BTH_ENUMERATOR_INFO</a>.


### -field ENUMERATOR_TYPE_DEVICE


### -field ENUMERATOR_TYPE_MAX

For internal use only. Do not use.


## -remarks



A value from this enumeration is returned as the 
    <b>EnumeratorType</b> member of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536643">BTH_ENUMERATOR_INFO</a> structure, which the 
    <a href="https://msdn.microsoft.com/43cd8e6b-5710-4308-a7c4-fb6f14940977">
    IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO</a> returns in its output buffer.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536643">BTH_ENUMERATOR_INFO</a>



<a href="https://msdn.microsoft.com/43cd8e6b-5710-4308-a7c4-fb6f14940977">
   IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO</a>
 

 

