---
UID: NS:hbapiwmi._SM_SendTEST_IN
title: "_SM_SendTEST_IN"
author: windows-driver-content
description: The SM_SendTEST_IN structure is used to provide input parameters to the SM_SendTEST method.
old-location: storage\sm_sendtest_in.htm
old-project: storage
ms.assetid: 5bb0620e-b271-4af6-b528-b904910b8a6c
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PSM_SendTEST_IN structure pointer [Storage Devices], SM_SendTEST_IN structure [Storage Devices], hbapiwmi/PSM_SendTEST_IN, PSM_SendTEST_IN, structs-Fibre_6d12c9e2-88bd-4803-893a-bb4e54604fad.xml, hbapiwmi/SM_SendTEST_IN, _SM_SendTEST_IN, *PSM_SendTEST_IN, SM_SendTEST_IN, storage.sm_sendtest_in
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
-	SM_SendTEST_IN
product: Windows
targetos: Windows
req.typenames: "*PSM_SendTEST_IN, SM_SendTEST_IN"
---

# _SM_SendTEST_IN structure


## -description


The SM_SendTEST_IN structure is used to provide input parameters to the SM_SendTEST method.


## -syntax


````
typedef struct _SM_SendTEST_IN {
  UCHAR HbaPortWWN[8];
  UCHAR DestWWN[8];
  ULONG DestFCID;
  ULONG ReqBufferSize;
  UCHAR ReqBuffer[1];
} SM_SendTEST_IN, *PSM_SendTEST_IN;
````


## -struct-fields




### -field HbaPortWWN

The local HBA port worldwide name (WWN).


### -field DestWWN

The remote HBA port worldwide name (WWN) to which the command will be sent.


### -field DestFCID

The address identifier of the remote port.


### -field ReqBufferSize

The request buffer size.


### -field ReqBuffer

The request buffer data.


## -remarks


The WMI tool suite generates a declaration of the SM_SendTEST_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.


