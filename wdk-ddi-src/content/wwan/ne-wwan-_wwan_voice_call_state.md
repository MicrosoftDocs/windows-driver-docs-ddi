---
UID: NE:wwan._WWAN_VOICE_CALL_STATE
title: "_WWAN_VOICE_CALL_STATE"
author: windows-driver-content
description: The WWAN_VOICE_CALL_STATE enumeration lists the different voice call states that are supported by the MB device.
old-location: netvista\wwan_voice_call_state.htm
old-project: netvista
ms.assetid: 50b85fc0-b84a-4c1d-9d7b-4b91150f8e76
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWWAN_VOICE_CALL_STATE, PWWAN_VOICE_CALL_STATE, PWWAN_VOICE_CALL_STATE enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_VOICE_CALL_STATE, WWAN_VOICE_CALL_STATE enumeration [Network Drivers Starting with Windows Vista], WwanRef_65c4ae25-c50f-4527-95fd-043730c736e4.xml, WwanVoiceCallStateHangUp, WwanVoiceCallStateInProgress, WwanVoiceCallStateMaximum, WwanVoiceCallStateNone, _WWAN_VOICE_CALL_STATE, netvista.wwan_voice_call_state, wwan/PWWAN_VOICE_CALL_STATE, wwan/WWAN_VOICE_CALL_STATE, wwan/WwanVoiceCallStateHangUp, wwan/WwanVoiceCallStateInProgress, wwan/WwanVoiceCallStateMaximum, wwan/WwanVoiceCallStateNone"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
-	wwan.h
api_name:
-	WWAN_VOICE_CALL_STATE
product: Windows
targetos: Windows
req.typenames: WWAN_VOICE_CALL_STATE, *PWWAN_VOICE_CALL_STATE
req.product: Windows 10 or later.
---

# _WWAN_VOICE_CALL_STATE enumeration


## -description


The WWAN_VOICE_CALL_STATE enumeration lists the different voice call states that are supported by the
  MB device.


## -syntax


````
typedef enum _WWAN_VOICE_CALL_STATE { 
  WwanVoiceCallStateNone        = 0,
  WwanVoiceCallStateInProgress,
  WwanVoiceCallStateHangUp,
  WwanVoiceCallStateMaximum
} WWAN_VOICE_CALL_STATE, *PWWAN_VOICE_CALL_STATE;
````


## -enum-fields




### -field WwanVoiceCallStateNone

The device does not support voice calls, or there is no voice call currently in progress.


### -field WwanVoiceCallStateInProgress

A voice call is currently in progress. This value applies only to devices whose voice class is 
     <b>WwanVoiceClassSeparateVoiceData</b>.


### -field WwanVoiceCallStateHangUp

A voice call is completed. This value applies only to devices whose voice class is 
     <b>WwanVoiceClassSeparateVoiceData</b>.


### -field WwanVoiceCallStateMaximum

The total number of supported voice call states.


## -see-also

<a href="..\wwan\ns-wwan-_wwan_context_state.md">WWAN_CONTEXT_STATE</a>



 

 


