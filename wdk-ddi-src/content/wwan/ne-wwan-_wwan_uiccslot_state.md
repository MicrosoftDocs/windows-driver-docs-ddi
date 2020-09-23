---
UID: NE:wwan._WWAN_UICCSLOT_STATE
title: _WWAN_UICCSLOT_STATE (wwan.h)
description: The WWAN_UICCSLOT_STATE enumeration lists the different states of a UICC (SIM) card slot on a modem. The slot state represents a summary of both the slot state and the card state.
old-location: netvista\wwan_uiccslot_state.htm
tech.root: netvista
ms.assetid: 63A3C2AA-6EBF-469D-933A-C51F5EC31C47
ms.date: 05/02/2018
keywords: ["WWAN_UICCSLOT_STATE enumeration"]
ms.keywords: "*PWWAN_UICCSLOT_STATE, UICCSlotStateActive, UICCSlotStateEmpty, UICCSlotStateError, UICCSlotStateNotReady, UICCSlotStateOff, UICCSlotStateOffEmpty, UICCSlotStateUnknown, WWAN_UICCSLOT_STATE, WWAN_UICCSLOT_STATE enumeration [Network Drivers Starting with Windows Vista], _WWAN_UICCSLOT_STATE, netvista.wwan_uiccslot_state, wwan/UICCSlotStateActive, wwan/UICCSlotStateEmpty, wwan/UICCSlotStateError, wwan/UICCSlotStateNotReady, wwan/UICCSlotStateOff, wwan/UICCSlotStateOffEmpty, wwan/UICCSlotStateUnknown, wwan/WWAN_UICCSLOT_STATE"
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
targetos: Windows
req.typenames: WWAN_UICCSLOT_STATE, *PWWAN_UICCSLOT_STATE
f1_keywords:
 - _WWAN_UICCSLOT_STATE
 - wwan/_WWAN_UICCSLOT_STATE
 - PWWAN_UICCSLOT_STATE
 - wwan/PWWAN_UICCSLOT_STATE
 - WWAN_UICCSLOT_STATE
 - wwan/WWAN_UICCSLOT_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - WWAN_UICCSLOT_STATE
---

# _WWAN_UICCSLOT_STATE enumeration


## -description

The <b>WWAN_UICCSLOT_STATE</b> enumeration lists the different states of a UICC (SIM) card slot on a modem. The slot state represents a summary of both the slot state and the card state.

## -enum-fields

### -field WwanUiccSlotStateUnknown

The modem is still in the process of initializing so the SIM slot state is not deterministic.

### -field WwanUiccSlotStateOffEmpty

The card slot is powered off and empty. An implementation that is unable to determine the presence of a card in a slot that is powered off reports its state as <i>Off</i>.

### -field WwanUiccSlotStateOff

The card slot is powered off and a card is present.

### -field WwanUiccSlotStateEmpty

The card slot is powered on but no card is present.

### -field WwanUiccSlotStateNotReady

The card in the slot is not ready. In other words, it has been reset but has not finished initializing. It cannot be used at this time.

### -field WwanUiccSlotStateActive

The card in the slot is available and ready to accept commands. This has no association with the SIM PIN locked state.

### -field WwanUiccSlotStateError

The card in the slot is in an error state and cannot be used.

### -field WwanUiccSlotStateActiveEsim

The card in the slot is an eSIM with an active profile, and it is ready to accept commands.

### -field WwanUiccSlotStateActiveEsimNoProfile

The card in the slot is an eSIM with no profiles or active profiles, and it is ready to accept commands.

### -field WwanUiccSlotStateMax

The maximum value for this enumeration.

## -remarks

The set of reported states is constrained by the capability of the slot hardware. In the most restrictive case, the slot hardware may only be able to determine that a card is present when it is powered on and active; in such a case the <b>OffEmpty</b> and <b>Off</b> states will not be reported.

## -see-also

<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_slot_info">WWAN_SLOT_INFO</a>