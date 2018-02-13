---
UID: NS:hbapiwmi._SM_SendRNID_IN
title: "_SM_SendRNID_IN"
author: windows-driver-content
description: The SM_SendRNID_IN structure is used to provide input parameters to the SM_SendRNID method.
old-location: storage\sm_sendrnid_in.htm
old-project: storage
ms.assetid: 7d94fc94-bfc6-4666-a321-71a0643f3140
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PSM_SendRNID_IN, SM_SendRNID_IN structure [Storage Devices], hbapiwmi/PSM_SendRNID_IN, storage.sm_sendrnid_in, structs-Fibre_61452dff-7706-4a0a-838a-5220f7117668.xml, PSM_SendRNID_IN structure pointer [Storage Devices], _SM_SendRNID_IN, *PSM_SendRNID_IN, SM_SendRNID_IN, hbapiwmi/SM_SendRNID_IN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
-	hbapiwmi.h
apiname:
-	SM_SendRNID_IN
product: Windows
targetos: Windows
req.typenames: "*PSM_SendRNID_IN, SM_SendRNID_IN"
---

# _SM_SendRNID_IN structure


## -description


The SM_SendRNID_IN structure is used to provide input parameters to the SM_SendRNID method.


## -syntax


````
typedef struct _SM_SendRNID_IN {
  UCHAR HbaPortWWN[8];
  UCHAR DestWWN[8];
  ULONG DestFCID;
  ULONG NodeIdDataFormat;
  ULONG InRespBufferMaxSize;
} SM_SendRNID_IN, *PSM_SendRNID_IN;
````


## -struct-fields




### -field HbaPortWWN

The worldwide name (WWN) of the local port.


### -field DestWWN

The worldwide name (WWN) of the destination port.


### -field DestFCID

The address identifier of the destination port.


### -field NodeIdDataFormat

The node identification data format.


### -field InRespBufferMaxSize

The maximum response buffer size.


## -remarks



The WMI tool suite generates a declaration of the SM_SendRNID_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.



