---
UID: NS:61883._CMP_GET_PLUG_HANDLE
title: _CMP_GET_PLUG_HANDLE (61883.h)
description: This structure is used in getting the handle of a plug.
old-location: ieee\cmp_get_plug_handle.htm
tech.root: IEEE
ms.assetid: 4EDEE2EE-7B42-4CC9-8CFC-4690193C5D4D
ms.date: 02/15/2018
keywords: ["CMP_GET_PLUG_HANDLE structure"]
ms.keywords: "*PCMP_GET_PLUG_HANDLE, 61883/CMP_GET_PLUG_HANDLE, 61883/PCMP_GET_PLUG_HANDLE, CMP_GET_PLUG_HANDLE, CMP_GET_PLUG_HANDLE structure [Buses], IEEE.cmp_get_plug_handle, PCMP_GET_PLUG_HANDLE, PCMP_GET_PLUG_HANDLE structure pointer [Buses], _CMP_GET_PLUG_HANDLE"
f1_keywords:
 - "61883/CMP_GET_PLUG_HANDLE"
 - "CMP_GET_PLUG_HANDLE"
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
- CMP_GET_PLUG_HANDLE
targetos: Windows
req.typenames: CMP_GET_PLUG_HANDLE, *PCMP_GET_PLUG_HANDLE
---

# _CMP_GET_PLUG_HANDLE structure


## -description


This structure is used in getting the handle of a plug. The  request retrieves a unique handle associated with an input or output plug. The plug handle is required for all operations on the plug. A driver uses a plug handle to get the state of a plug, modify plug settings, or delete a plug. A driver can delete only plugs it has previously created. 


## -struct-fields




### -field PlugNum

The number of the plug whose handle was returned by the Av61883_CreatePlug request that created the plug.


### -field Type

The type of the plug. This can be CMP_PlugOut for an output plug, or CMP_PlugIn for an input plug.


### -field hPlug

On output, a handle to the plug specified with PlugNum and Type.


## -remarks



If successful, the IEC-61883 protocol driver sets <b>Irp->IoStatus.Status </b>to STATUS_SUCCESS. 

If an incorrect parameter is passed in, the protocol driver sets <b>Irp->IoStatus.Status </b>to STATUS_INVALID_PARAMETER.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_av_61883_request">AV_61883_REQUEST</a>
 

 

