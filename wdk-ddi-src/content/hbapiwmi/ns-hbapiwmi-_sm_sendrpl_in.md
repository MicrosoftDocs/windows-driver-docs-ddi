---
UID: NS:hbapiwmi._SM_SendRPL_IN
title: "_SM_SendRPL_IN"
author: windows-driver-content
description: The SM_SendRPL_IN structure is used to provide input parameters to the SM_SendRPL method.
old-location: storage\sm_sendrpl_in.htm
old-project: storage
ms.assetid: 5d97b852-57ba-4696-879b-d93a8f539304
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PSM_SendRPL_IN structure pointer [Storage Devices], SM_SendRPL_IN structure [Storage Devices], PSM_SendRPL_IN, SM_SendRPL_IN, _SM_SendRPL_IN, hbapiwmi/SM_SendRPL_IN, hbapiwmi/PSM_SendRPL_IN, *PSM_SendRPL_IN, storage.sm_sendrpl_in, structs-Fibre_54275ca2-35b3-43f4-a62d-63c296b14663.xml
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
-	SM_SendRPL_IN
product: Windows
targetos: Windows
req.typenames: SM_SendRPL_IN, *PSM_SendRPL_IN
---

# _SM_SendRPL_IN structure


## -description


The SM_SendRPL_IN structure is used to provide input parameters to the SM_SendRPL method.


## -syntax


````
typedef struct _SM_SendRPL_IN {
  UCHAR HbaPortWWN[8];
  UCHAR AgentWWN[8];
  ULONG AgentDomain;
  ULONG PortIndex;
  ULONG InRespBufferMaxSize;
} SM_SendRPL_IN, *PSM_SendRPL_IN;
````


## -struct-fields




### -field HbaPortWWN

A worldwide name (WWN) for the local port through which the read port list (RPL) command is sent.


### -field AgentWWN

A worldwide name (WWN) for the port that is to be queried for a list of ports of type FC_Port. For a definition of FC_Port, see the T11 committee's <i>Fibre Channel HBA API</i> specification<i>.</i>


### -field AgentDomain

The domain number for the domain controller that is to be queried for a list of ports of type FC_Port. For a definition of FC_Port, see the T11 committee's <i>Fibre Channel HBA API</i> specification.


### -field PortIndex

The port index of the first port in the list of ports of type FC_Port to be returned.


### -field InRespBufferMaxSize

The response buffer size.


## -remarks



The WMI tool suite generates a declaration of the SM_SendRPL_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.



