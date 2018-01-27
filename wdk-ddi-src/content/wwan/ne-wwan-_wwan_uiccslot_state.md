---
UID: NE:wwan._WWAN_UICCSLOT_STATE
title: _WWAN_UICCSLOT_STATE
author: windows-driver-content
description: The WWAN_UICCSLOT_STATE enumeration lists the different states of a UICC (SIM) card slot on a modem. The slot state represents a summary of both the slot state and the card state.
old-location: netvista\wwan_uiccslot_state.htm
old-project: netvista
ms.assetid: 63A3C2AA-6EBF-469D-933A-C51F5EC31C47
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wwan/UICCSlotStateNotReady, UICCSlotStateError, wwan/UICCSlotStateUnknown, UICCSlotStateOffEmpty, _WWAN_UICCSLOT_STATE, netvista.wwan_uiccslot_state, UICCSlotStateEmpty, WWAN_UICCSLOT_STATE enumeration [Network Drivers Starting with Windows Vista], UICCSlotStateOff, UICCSlotStateActive, UICCSlotStateUnknown, wwan/UICCSlotStateActive, wwan/UICCSlotStateError, wwan/UICCSlotStateEmpty, UICCSlotStateNotReady, *PWWAN_UICCSLOT_STATE, wwan/UICCSlotStateOff, WWAN_UICCSLOT_STATE, wwan/UICCSlotStateOffEmpty, wwan/WWAN_UICCSLOT_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703
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
-	wwan.h
apiname: 
-	WWAN_UICCSLOT_STATE
product: Windows
targetos: Windows
req.typenames: WWAN_UICCSLOT_STATE, *PWWAN_UICCSLOT_STATE
req.product: Windows 10 or later.
---

# _WWAN_UICCSLOT_STATE enumeration


## -description


The <b>WWAN_UICCSLOT_STATE</b> enumeration lists the different states of a UICC (SIM) card slot on a modem. The slot state represents a summary of both the slot state and the card state.


## -syntax


````
typedef enum _WWAN_UICCSLOT_STATE { 
  UICCSlotStateUnknown,
  UICCSlotStateOffEmpty,
  UICCSlotStateOff,
  UICCSlotStateEmpty,
  UICCSlotStateNotReady,
  UICCSlotStateActive,
  UICCSlotStateError
} WWAN_UICCSLOT_STATE;
````


## -enum-fields




### -field WwanUiccSlotStateUnknown



### -field WwanUiccSlotStateOffEmpty



### -field WwanUiccSlotStateOff



### -field WwanUiccSlotStateEmpty



### -field WwanUiccSlotStateNotReady



### -field WwanUiccSlotStateActive



### -field WwanUiccSlotStateError



### -field WwanUiccSlotStateActiveEsim



### -field WwanUiccSlotStateActiveEsimNoProfile



### -field WwanUiccSlotStateMax




#### - UICCSlotStateError

The card in the slot is in an error state and cannot be used.


#### - UICCSlotStateOffEmpty

The card slot is powered off and empty. An implementation that is unable to determine the presence of a card in a slot that is powered off reports its state as <i>Off</i>.


#### - UICCSlotStateOff

The card slot is powered off and a card is present.


#### - UICCSlotStateActive

The card in the slot is available and ready to accept commands. This has no association with the SIM PIN locked state.


#### - UICCSlotStateUnknown

The modem is still in the process of initializing so the SIM slot state is not deterministic.


#### - UICCSlotStateNotReady

The card in the slot is not ready; i.e., it has been reset but has not finished initializing. It cannot be used at this time.


#### - UICCSlotStateEmpty

The card slot is powered on but no card is present.


## -remarks


The set of reported states is constrained by the capability of the slot hardware. In the most restrictive case, the slot hardware may only be able to determine that a card is present when it is powered on and active; in such a case the <b>OffEmpty</b> and <b>Off</b> states will not be reported.



## -see-also

<a href="..\wwan\ns-wwan-_wwan_slot_info.md">WWAN_SLOT_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_UICCSLOT_STATE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

