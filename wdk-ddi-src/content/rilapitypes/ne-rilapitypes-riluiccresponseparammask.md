---
UID: NE:rilapitypes.RILUICCRESPONSEPARAMMASK
title: RILUICCRESPONSEPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccresponseparammask_2.htm
old-project: netvista
ms.assetid: b281375a-a2bf-4b19-af94-a3902cf462b2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILUICCRESPONSEPARAMMASK, RILUICCRESPONSEPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_SR_ALL, RIL_PARAM_SR_RESPONSE, RIL_PARAM_SR_RESPONSESIZE, RIL_PARAM_SR_STATUSWORD2, netvista.riluiccresponseparammask_2, rilapitypes/RILUICCRESPONSEPARAMMASK, rilapitypes/RIL_PARAM_SR_ALL, rilapitypes/RIL_PARAM_SR_RESPONSE, rilapitypes/RIL_PARAM_SR_RESPONSESIZE, rilapitypes/RIL_PARAM_SR_STATUSWORD2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.lib: NtosKrnl.exe
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
-	RILUICCRESPONSEPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILUICCRESPONSEPARAMMASK
req.product: Windows 10 or later.
---

# RILUICCRESPONSEPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILUICCRESPONSEPARAMMASK { 
  RIL_PARAM_SR_STATUSWORD2,
  RIL_PARAM_SR_RESPONSESIZE,
  RIL_PARAM_SR_RESPONSE,
  RIL_PARAM_SR_ALL
} RILUICCRESPONSEPARAMMASK;
````


## -enum-fields




### -field RIL_PARAM_SR_STATUSWORD1


### -field RIL_PARAM_SR_STATUSWORD2


### -field RIL_PARAM_SR_RESPONSESIZE


### -field RIL_PARAM_SR_RESPONSE


### -field RIL_PARAM_SR_ALL

