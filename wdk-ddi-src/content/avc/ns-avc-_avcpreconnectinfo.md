---
UID: NS:avc._AVCPRECONNECTINFO
title: "_AVCPRECONNECTINFO"
author: windows-driver-content
description: The AVCPRECONNECTINFO structure is used to initialize a subunit driver and establish pin connections.
old-location: stream\avcpreconnectinfo.htm
old-project: stream
ms.assetid: 828ce6cf-f47a-4487-8c45-887f2ace8202
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PAVCPRECONNECTINFO, AVCPRECONNECTINFO, AVCPRECONNECTINFO structure [Streaming Media Devices], PAVCPRECONNECTINFO, PAVCPRECONNECTINFO structure pointer [Streaming Media Devices], _AVCPRECONNECTINFO, avc/AVCPRECONNECTINFO, avc/PAVCPRECONNECTINFO, avcref_c38bc8dd-8218-40ea-95b6-c5376fa6273c.xml, stream.avcpreconnectinfo"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: avc.h
req.include-header: Avc.h
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
-	avc.h
api_name:
-	AVCPRECONNECTINFO
product: Windows
targetos: Windows
req.typenames: AVCPRECONNECTINFO, *PAVCPRECONNECTINFO
---

# _AVCPRECONNECTINFO structure


## -description


The AVCPRECONNECTINFO structure is used to initialize a subunit driver and establish pin connections.


## -syntax


````
typedef struct _AVCPRECONNECTINFO {
  GUID           DeviceID;
  UCHAR          SubunitAddress[AVCCONNECTINFO_MAX_SUBUNITADDR_LEN];
  ULONG          SubunitPlugNumber;
  KSPIN_DATAFLOW DataFlow;
  ULONG          Flags;
  ULONG          UnitPlugNumber;
} AVCPRECONNECTINFO, *PAVCPRECONNECTINFO;
````


## -struct-fields




### -field DeviceID

A GUID representing the unit as a whole. All subunits within the same unit share the same GUID. No two units share the same GUID.


### -field SubunitAddress

The encoded subunit type and subunit ID of the subunit.


### -field SubunitPlugNumber

The plug number (within the subunit) described by the AVCPRECONNECTINFO structure.


### -field DataFlow

The direction of data flow on this subunit plug. Destination plugs have KSPIN_DATAFLOW_IN; source plugs have KSPIN_DATAFLOW_OUT.


### -field Flags

A bitmap with one or more bits set from the KSPIN_FLAG_AVC enumeration.


### -field UnitPlugNumber

The plug number (within the subunit) described by the AVCPRECONNECTINFO structure.


## -remarks



This structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554154">AVC_FUNCTION_GET_CONNECTINFO</a> function code.

This structure is used only as member of the AVC_PRECONNECT_INFO structure. It is not used by itself.




## -see-also

<a href="..\avc\ns-avc-_avc_preconnect_info.md">AVC_PRECONNECT_INFO</a>



<a href="..\avc\ne-avc-_kspin_flag_avc.md">KSPIN_FLAG_AVC</a>



 

 


