---
UID: NS:61883._CMP_SET_PLUG
title: _CMP_SET_PLUG (61883.h)
description: This structure is used to assign settings to a plug.
old-location: ieee\cmp_set_plug.htm
tech.root: IEEE
ms.assetid: 2C47165D-9D04-46C8-A1EC-04E6F32AE516
ms.date: 02/15/2018
ms.keywords: "*PCMP_SET_PLUG, 61883/CMP_SET_PLUG, 61883/PCMP_SET_PLUG, CMP_SET_PLUG, CMP_SET_PLUG structure [Buses], IEEE.cmp_set_plug, PCMP_SET_PLUG, PCMP_SET_PLUG structure pointer [Buses], _CMP_SET_PLUG"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- 61883.h
api_name:
- CMP_SET_PLUG
product:
- Windows
targetos: Windows
req.typenames: CMP_SET_PLUG, *PCMP_SET_PLUG
---

# _CMP_SET_PLUG structure


## -description


This structure is used to assign settings to a plug.he  request changes transmission settings for a plug control register. Only a driver that created a plug is allowed to set the contents of that plug. 


## -struct-fields




### -field hPlug

On input, a handle to the plug.


### -field Pcr

On input, an <a href="https://msdn.microsoft.com/library/windows/hardware/ff537010">AV_PCR</a> structure that contains settings for the plug.


## -remarks



If successful, the IEC-61883 protocol driver sets <b>Irp->IoStatus.Status </b>to STATUS_SUCCESS. 

If an incorrect parameter is passed in, the protocol driver sets <b>Irp->IoStatus.Status </b>to STATUS_INVALID_PARAMETER.

If a driver attempts to set the contents of a plug register it did not create, the protocol driver sets <b>Irp->IoStatus.Status </b>to STATUS_ACCESS_DENIED.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>
 

 

