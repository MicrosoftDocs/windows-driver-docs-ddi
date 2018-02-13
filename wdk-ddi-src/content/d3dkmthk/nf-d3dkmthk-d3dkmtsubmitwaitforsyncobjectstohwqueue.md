---
UID: NF:d3dkmthk.D3DKMTSubmitWaitForSyncObjectsToHwQueue
title: D3DKMTSubmitWaitForSyncObjectsToHwQueue function
author: windows-driver-content
description: Used to submit a wait to the hardware queue.
old-location: display\d3dkmtsubmitwaitforsyncobjectstohwqueue.htm
old-project: display
ms.assetid: E068ECD0-059A-46E1-9D9E-64EA81B73BD6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTSubmitWaitForSyncObjectsToHwQueue, D3DKMTSubmitWaitForSyncObjectsToHwQueue function [Display Devices], display.d3dkmtsubmitwaitforsyncobjectstohwqueue, d3dkmthk/D3DKMTSubmitWaitForSyncObjectsToHwQueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
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
req.lib: Tbd
req.dll: Tbd
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	tbd
apiname:
-	D3DKMTSubmitWaitForSyncObjectsToHwQueue
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTSubmitWaitForSyncObjectsToHwQueue function


## -description


Used to submit a wait to the hardware queue.


## -syntax


````
NTSTATUS APIENTRY D3DKMTSubmitWaitForSyncObjectsToHwQueue(
  _In_ const D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE *submitWaitForSyncObjectsToHwQueue
);
````


## -parameters




### -param D3DKMT_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE

TBD




#### - submitWaitForSyncObjectsToHwQueue [in]

A structure holding the information needed to submit a wait to the hardware queue.


## -returns



Returns STATUS_SUCCESS if called successfully. 



