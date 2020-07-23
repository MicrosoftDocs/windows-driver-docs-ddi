---
UID: NS:61883._SET_CMP_ADDRESS_TYPE
title: _SET_CMP_ADDRESS_TYPE (61883.h)
description: The SET_CMP_ADDRESS_TYPE structure is used in conjunction with the Av61883_SetUnitInfo request to set the parameters that the IEC-61883 protocol driver should use when capturing and transmitting isochronous packets.
old-location: ieee\set_cmp_address_type.htm
tech.root: IEEE
ms.assetid: b08588a2-d786-44c1-a265-0f7fef9ecd6a
ms.date: 02/15/2018
keywords: ["_SET_CMP_ADDRESS_TYPE structure"]
ms.keywords: "*PSET_CMP_ADDRESS_TYPE, 61883/PSET_CMP_ADDRESS_TYPE, 61883/SET_CMP_ADDRESS_TYPE, 61883_structures_35b30fc9-69a6-4599-8d76-5aaf35104346.xml, IEEE.set_cmp_address_type, PSET_CMP_ADDRESS_TYPE, PSET_CMP_ADDRESS_TYPE structure pointer [Buses], SET_CMP_ADDRESS_TYPE, SET_CMP_ADDRESS_TYPE structure [Buses], _SET_CMP_ADDRESS_TYPE"
f1_keywords:
 - "61883/SET_CMP_ADDRESS_TYPE"
 - "SET_CMP_ADDRESS_TYPE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- 61883.h
api_name:
- SET_CMP_ADDRESS_TYPE
targetos: Windows
req.typenames: SET_CMP_ADDRESS_TYPE, *PSET_CMP_ADDRESS_TYPE
---

# _SET_CMP_ADDRESS_TYPE structure


## -description


The SET_CMP_ADDRESS_TYPE structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537002">Av61883_SetUnitInfo</a> request to set the parameters that the IEC-61883 protocol driver should use when capturing and transmitting isochronous packets. 


## -struct-fields




### -field Type

Indicates what kind of address range plugs can be accessed in. Possible values are:





#### CMP_ADDRESS_TYPE_GLOBAL

This requests the default behavior. All plugs created on the local system are within a global address range, accessible by any node on the 1394 bus.



#### CMP_ADDRESS_TYPE_EXCLUSIVE

This flag must be set before any plugs are created or removed within the driver. When this flag is set, all plugs created within the driver are in an exclusive address range, only accessible to the device for which the driver is loaded.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537002">Av61883_SetUnitInfo</a>
 

 

