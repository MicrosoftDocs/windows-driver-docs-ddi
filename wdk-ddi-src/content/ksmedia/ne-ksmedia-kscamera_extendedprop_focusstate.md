---
UID: NE:ksmedia.KSCAMERA_EXTENDEDPROP_FOCUSSTATE
title: KSCAMERA_EXTENDEDPROP_FOCUSSTATE
author: windows-driver-content
description: This enumeration contains the focus states.
old-location: stream\kscamera_extendedprop_focusstate.htm
old-project: stream
ms.assetid: 2B74DB73-1D27-49E6-B1D8-8246FCE2F5E1
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ksmedia/KSCAMERA_EXTENDEDPROP_FOCUSSTATE_LOST, KSCAMERA_EXTENDEDPROP_FOCUSSTATE_LOST, ksmedia/KSCAMERA_EXTENDEDPROP_FOCUSSTATE_SEARCHING, ksmedia/KSCAMERA_EXTENDEDPROP_FOCUSSTATE_FAILED, ksmedia/KSCAMERA_EXTENDEDPROP_FOCUSSTATE_FOCUSED, ksmedia/KSCAMERA_EXTENDEDPROP_FOCUSSTATE_UNINITIALIZED, stream.kscamera_extendedprop_focusstate, KSCAMERA_EXTENDEDPROP_FOCUSSTATE_SEARCHING, KSCAMERA_EXTENDEDPROP_FOCUSSTATE_FOCUSED, KSCAMERA_EXTENDEDPROP_FOCUSSTATE, ksmedia/KSCAMERA_EXTENDEDPROP_FOCUSSTATE, KSCAMERA_EXTENDEDPROP_FOCUSSTATE_UNINITIALIZED, KSCAMERA_EXTENDEDPROP_FOCUSSTATE_FAILED, KSCAMERA_EXTENDEDPROP_FOCUSSTATE enumeration [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ksmedia.h
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
-	Ksmedia.h
apiname:
-	KSCAMERA_EXTENDEDPROP_FOCUSSTATE
product: Windows
targetos: Windows
req.typenames: KSCAMERA_EXTENDEDPROP_FOCUSSTATE
---

# KSCAMERA_EXTENDEDPROP_FOCUSSTATE enumeration


## -description


This enumeration contains the focus states.


## -syntax


````
typedef enum  { 
  KSCAMERA_EXTENDEDPROP_FOCUSSTATE_UNINITIALIZED  = 0,
  KSCAMERA_EXTENDEDPROP_FOCUSSTATE_LOST,
  KSCAMERA_EXTENDEDPROP_FOCUSSTATE_SEARCHING,
  KSCAMERA_EXTENDEDPROP_FOCUSSTATE_FOCUSED,
  KSCAMERA_EXTENDEDPROP_FOCUSSTATE_FAILED
} KSCAMERA_EXTENDEDPROP_FOCUSSTATE;
````


## -enum-fields




#### - KSCAMERA_EXTENDEDPROP_FOCUSSTATE_UNINITIALIZED

The focus state is not initialized.


#### - KSCAMERA_EXTENDEDPROP_FOCUSSTATE_LOST

The focus state is lost.


#### - KSCAMERA_EXTENDEDPROP_FOCUSSTATE_SEARCHING

The focus state is searching.


#### - KSCAMERA_EXTENDEDPROP_FOCUSSTATE_FOCUSED

The focus state is focused.


#### - KSCAMERA_EXTENDEDPROP_FOCUSSTATE_FAILED

The focus state is failed.

