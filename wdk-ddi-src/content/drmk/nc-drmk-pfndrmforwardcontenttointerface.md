---
UID: NC:drmk.PFNDRMFORWARDCONTENTTOINTERFACE
title: PFNDRMFORWARDCONTENTTOINTERFACE
author: windows-driver-content
description: This callback function is reserved for system use.
old-location: audio\pfndrmforwardcontenttointerface.htm
old-project: audio
ms.assetid: DFD077B7-307B-439B-828D-DC225FC5AAA0
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audio.pfndrmforwardcontenttointerface, DRMForwardContentToInterface callback function [Audio Devices], DRMForwardContentToInterface, PFNDRMFORWARDCONTENTTOINTERFACE, PFNDRMFORWARDCONTENTTOINTERFACE, drmk/DRMForwardContentToInterface, DRMForwardContentToInterface callback function [Audio Devices], DRMForwardContentToInterface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: drmk.h
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
-	UserDefined
apilocation:
-	Drmk.h
apiname:
-	DRMForwardContentToInterface
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# PFNDRMFORWARDCONTENTTOINTERFACE callback


## -description


This callback function is reserved for system use.


## -prototype


````
PFNDRMFORWARDCONTENTTOINTERFACE DRMForwardContentToInterface;

NTSTATUS DRMForwardContentToInterface(
  _In_ ULONG     ContentId,
  _In_ PUNKNOWN  pUnknown,
  _In_ ULONG     NumMethods
)
{ ... }

typedef PFNDRMFORWARDCONTENTTOINTERFACE DRMForwardContentToInterface;
````


## -parameters




### -param ContentId [in]

This parameter is reserved for system use.


### -param pUnknown [in]

This parameter is reserved for system use.


### -param NumMethods [in]

This parameter is reserved for system use.


## -returns


This return value is reserved for system use.


