---
UID: NE:wwan._WWAN_UICC_PASSTHROUGH_ACTION
title: _WWAN_UICC_PASSTHROUGH_ACTION (wwan.h)
description: The WWAN_UICC_PASSTHROUGH_ACTION enumeration defines the passthrough action specified by the MB host for a modem miniport adapter after it resets a UICC smart card.
old-location: netvista\wwan_uicc_passthrough_action.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WWAN_UICC_PASSTHROUGH_ACTION enumeration"]
ms.keywords: "*PWWAN_UICC_PASSTHROUGH_ACTION, WWAN_UICC_PASSTHROUGH_ACTION, WWAN_UICC_PASSTHROUGH_ACTION enumeration [Network Drivers Starting with Windows Vista], WwanUiccPassThroughActionMaximum, WwanUiccPassThroughDisable, WwanUiccPassThroughEnable, _WWAN_UICC_PASSTHROUGH_ACTION, netvista.wwan_uicc_passthrough_action, wwan/WWAN_UICC_PASSTHROUGH_ACTION, wwan/WwanUiccPassThroughActionMaximum, wwan/WwanUiccPassThroughDisable, wwan/WwanUiccPassThroughEnable"
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
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
req.typenames: WWAN_UICC_PASSTHROUGH_ACTION, *PWWAN_UICC_PASSTHROUGH_ACTION
f1_keywords:
 - _WWAN_UICC_PASSTHROUGH_ACTION
 - wwan/_WWAN_UICC_PASSTHROUGH_ACTION
 - PWWAN_UICC_PASSTHROUGH_ACTION
 - wwan/PWWAN_UICC_PASSTHROUGH_ACTION
 - WWAN_UICC_PASSTHROUGH_ACTION
 - wwan/WWAN_UICC_PASSTHROUGH_ACTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_UICC_PASSTHROUGH_ACTION
 - PWWAN_UICC_PASSTHROUGH_ACTION
 - WWAN_UICC_PASSTHROUGH_ACTION
---

# _WWAN_UICC_PASSTHROUGH_ACTION enumeration


## -description

The <b>WWAN_UICC_PASSTHROUGH_ACTION</b> enumeration defines the passthrough action specified by the MB host for a modem miniport adapter after it resets a UICC smart card.

## -enum-fields

### -field WwanUiccPassThroughDisable

Indicates to disable passthrough to the UICC after reset. When UICC passthrough is disabled, the MB host treats the UICC as a regular Telecom UICC and expects a Telecom UICC file system to be present on the UICC.

### -field WwanUiccPassThroughEnable

Indicates to enable passthrough to the UICC after reset. When UICC passthrough is enabled, the modem miniport adapter treats the UICC as if it were in a passthrough mode that enables communication between the host and UICC, even if the UICC has no Telecom UICC file system. The miniport adapter does not send any APDUs to the card and does not interfere at any time with the communication between the host and the UICC.

### -field WwanUiccPassThroughActionMaximum

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.

## -see-also

<a href="/windows-hardware/drivers/network/mb-uicc-reset-operations">MB UICC reset operations</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_set_uicc_reset">WWAN_SET_UICC_RESET</a>

