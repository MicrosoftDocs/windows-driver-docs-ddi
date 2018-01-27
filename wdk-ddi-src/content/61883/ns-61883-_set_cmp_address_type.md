---
UID: NS:61883._SET_CMP_ADDRESS_TYPE
title: _SET_CMP_ADDRESS_TYPE
author: windows-driver-content
description: The SET_CMP_ADDRESS_TYPE structure is used in conjunction with the Av61883_SetUnitInfo request to set the parameters that the IEC-61883 protocol driver should use when capturing and transmitting isochronous packets.
old-location: ieee\set_cmp_address_type.htm
old-project: IEEE
ms.assetid: b08588a2-d786-44c1-a265-0f7fef9ecd6a
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PSET_CMP_ADDRESS_TYPE structure pointer [Buses], *PSET_CMP_ADDRESS_TYPE, 61883_structures_35b30fc9-69a6-4599-8d76-5aaf35104346.xml, SET_CMP_ADDRESS_TYPE, IEEE.set_cmp_address_type, PSET_CMP_ADDRESS_TYPE, _SET_CMP_ADDRESS_TYPE, SET_CMP_ADDRESS_TYPE structure [Buses], 61883/PSET_CMP_ADDRESS_TYPE, 61883/SET_CMP_ADDRESS_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 61883.h
req.include-header: 61883.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	61883.h
apiname: 
-	SET_CMP_ADDRESS_TYPE
product: Windows
targetos: Windows
req.typenames: *PSET_CMP_ADDRESS_TYPE, SET_CMP_ADDRESS_TYPE
---

# _SET_CMP_ADDRESS_TYPE structure


## -description


The SET_CMP_ADDRESS_TYPE structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537002">Av61883_SetUnitInfo</a> request to set the parameters that the IEC-61883 protocol driver should use when capturing and transmitting isochronous packets. 


## -syntax


````
typedef struct _SET_CMP_ADDRESS_TYPE {
  ULONG Type;
} SET_CMP_ADDRESS_TYPE, *PSET_CMP_ADDRESS_TYPE;
````


## -struct-fields




### -field Type

Indicates what kind of address range plugs can be accessed in. Possible values are:




##### - Type.CMP_ADDRESS_TYPE_EXCLUSIVE

This flag must be set before any plugs are created or removed within the driver. When this flag is set, all plugs created within the driver are in an exclusive address range, only accessible to the device for which the driver is loaded.


##### - Type.CMP_ADDRESS_TYPE_GLOBAL

This requests the default behavior. All plugs created on the local system are within a global address range, accessible by any node on the 1394 bus.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537002">Av61883_SetUnitInfo</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20SET_CMP_ADDRESS_TYPE structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

