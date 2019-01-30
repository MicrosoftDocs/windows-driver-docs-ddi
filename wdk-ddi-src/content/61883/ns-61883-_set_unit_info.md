---
UID: NS:61883._SET_UNIT_INFO
title: _SET_UNIT_INFO (61883.h)
description: This structure is used to set unit information.
old-location: ieee\set_unit_info.htm
tech.root: IEEE
ms.assetid: D4A9B507-E199-42EA-BC29-6F477BEC8D20
ms.date: 02/15/2018
ms.keywords: "*PSET_UNIT_INFO, 61883/PSET_UNIT_INFO, 61883/SET_UNIT_INFO, IEEE.set_unit_info, PSET_UNIT_INFO, PSET_UNIT_INFO structure pointer [Buses], SET_UNIT_INFO, SET_UNIT_INFO structure [Buses], _SET_UNIT_INFO"
ms.topic: struct
req.header: 61883.h
req.include-header: 
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	61883.h
api_name:
-	SET_UNIT_INFO
product:
- Windows
targetos: Windows
req.typenames: SET_UNIT_INFO, *PSET_UNIT_INFO
---

# _SET_UNIT_INFO structure


## -description


This structure is used to set unit information.

The Av61883_SetUnitInfo request sets the parameters that the IEC-61883 protocol driver should use when capturing and transmitting isochronous packets. 


## -struct-fields




### -field nLevel

On input, the level of information to retrieve. Can be one of the following:

SET_UNIT_INFO_DIAG_LEVEL

SET_UNIT_INFO_ISOCH_PARAMS

SET_CMP_ADDRESS_RANGE_TYPE


### -field Information

On input, if <b>nLevel</b> is SET_UNIT_INFO_DIAG_LEVEL, this member is a pointer to a caller-allocated and initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff538914">UNIT_DIAG_LEVEL</a> structure.

If <b>nLevel</b> is SET_UNIT_INFO_ISOCH_PARAMS, this member is a pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff538921">UNIT_ISOCH_PARAMS</a> structure. 

If <b>nLevel</b> is SET_CMP_ADDRESS_RANGE_TYPE, this member is a pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff538118">SET_CMP_ADDRESS_TYPE</a> structure. 


## -remarks



If successful, the IEC-61883 protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_SUCCESS. 

If an incorrect parameter is passed in, the protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_INVALID_PARAMETER.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>
 

 

