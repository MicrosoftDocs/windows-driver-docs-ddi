---
UID: NE:bthddi._ENUMERATOR_TYPE
title: "_ENUMERATOR_TYPE"
author: windows-driver-content
description: The ENUMERATOR_TYPE enumeration type is used to determine whether the enumerated device is associated with a service or a protocol. The ENUMERATOR_TYPE enumeration is intended for internal use only and should not be used by profile drivers.
old-location: bltooth\enumerator_type.htm
old-project: bltooth
ms.assetid: 2f8ae260-3a4c-44a5-85b7-e3ebcf21522b
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PENUMERATOR_TYPE, ENUMERATOR_TYPE, ENUMERATOR_TYPE enumeration [Bluetooth Devices], ENUMERATOR_TYPE_MAX, ENUMERATOR_TYPE_PROTOCOL, ENUMERATOR_TYPE_SERVICE, PENUMERATOR_TYPE, PENUMERATOR_TYPE enumeration pointer [Bluetooth Devices], _ENUMERATOR_TYPE, bltooth.enumerator_type, bth_enums_48fc8cf9-53b6-46fd-831a-f4a5c56ff3f1.xml, bthddi/ENUMERATOR_TYPE, bthddi/ENUMERATOR_TYPE_MAX, bthddi/ENUMERATOR_TYPE_PROTOCOL, bthddi/ENUMERATOR_TYPE_SERVICE, bthddi/PENUMERATOR_TYPE"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthddi.h
api_name:
-	ENUMERATOR_TYPE
product: Windows
targetos: Windows
req.typenames: ENUMERATOR_TYPE, *PENUMERATOR_TYPE
---

# _ENUMERATOR_TYPE enumeration


## -description


The ENUMERATOR_TYPE enumeration type is used to determine whether the enumerated device is associated
  with a service or a protocol. The ENUMERATOR_TYPE enumeration is intended for internal use only and should
  not be used by profile drivers.


## -syntax


````
typedef enum _ENUMERATOR_TYPE { 
  ENUMERATOR_TYPE_PROTOCOL  = 0,
  ENUMERATOR_TYPE_SERVICE   = 1,
  ENUMERATOR_TYPE_MAX       = 2
} ENUMERATOR_TYPE, *PENUMERATOR_TYPE;
````


## -enum-fields




### -field ENUMERATOR_TYPE_PROTOCOL

For internal use only. Do not use.


### -field ENUMERATOR_TYPE_SERVICE

This value should be specified for profile drivers. For more information about how this value is
     used, see 
     <a href="..\bthddi\ns-bthddi-_bth_enumerator_info.md">BTH_ENUMERATOR_INFO</a>.


### -field ENUMERATOR_TYPE_DEVICE


### -field ENUMERATOR_TYPE_MAX

For internal use only. Do not use.


## -remarks



A value from this enumeration is returned as the 
    <b>EnumeratorType</b> member of the 
    <a href="..\bthddi\ns-bthddi-_bth_enumerator_info.md">BTH_ENUMERATOR_INFO</a> structure, which the 
    <a href="..\bthioctl\ni-bthioctl-ioctl_internal_bthenum_get_enuminfo.md">
    IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO</a> returns in its output buffer.




## -see-also

<a href="..\bthioctl\ni-bthioctl-ioctl_internal_bthenum_get_enuminfo.md">
   IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO</a>



<a href="..\bthddi\ns-bthddi-_bth_enumerator_info.md">BTH_ENUMERATOR_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20ENUMERATOR_TYPE enumeration%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

