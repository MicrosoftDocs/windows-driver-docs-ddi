---
UID: NS:ntddrilapitypes.RILCONFPARTICIPANTSTATUS
title: RILCONFPARTICIPANTSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilconfparticipantstatus.htm
old-project: netvista
ms.assetid: 7eb0e06b-85f0-4b61-9ed0-2f35156fbb8c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RILCONFPARTICIPANTSTATUS, *LPRILCONFPARTICIPANTSTATUS, netvista.rilconfparticipantstatus, RILCONFPARTICIPANTSTATUS, RILCONFPARTICIPANTSTATUS structure [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddrilapitypes.h
apiname:
-	RILCONFPARTICIPANTSTATUS
product: Windows
targetos: Windows
req.typenames: RILCONFPARTICIPANTSTATUS, *LPRILCONFPARTICIPANTSTATUS
---

# RILCONFPARTICIPANTSTATUS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILCONFPARTICIPANTSTATUS {
  DWORD                    cbSize;
  DWORD                    dwParams;
  DWORD                    dwExecutor;
  DWORD                    dwID;
  BOOL                     bCallTransfer;
  RILADDRESS               raAddress;
  RILPARTICIPANTOPERATION  dwParticipantOp;
  DWORD                    dwSIPStatus;
} RILCONFPARTICIPANTSTATUS, RILCONFPARTICIPANTSTATUS;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwExecutor


### -field dwID


### -field bCallTransfer


### -field raAddress


### -field dwParticipantOp


### -field dwSIPStatus

