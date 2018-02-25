---
UID: NS:rilapitypes.RILCONFPARTICIPANTSTATUS
title: RILCONFPARTICIPANTSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilconfparticipantstatus_2.htm
old-project: netvista
ms.assetid: 3beafad2-7157-434a-a073-2b47026c8fc5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *LPRILCONFPARTICIPANTSTATUS, ,, A, C, F, I, L, N, O, P, R, RILCONFPARTICIPANTSTATUS, RILCONFPARTICIPANTSTATUS structure [Network Drivers Starting with Windows Vista], S, T, U, netvista.rilconfparticipantstatus_2, rilapitypes/RILCONFPARTICIPANTSTATUS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
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
-	rilapitypes.h
apiname:
-	RILCONFPARTICIPANTSTATUS
product: Windows
targetos: Windows
req.typenames: RILCONFPARTICIPANTSTATUS, *LPRILCONFPARTICIPANTSTATUS
req.product: Windows 10 or later.
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

